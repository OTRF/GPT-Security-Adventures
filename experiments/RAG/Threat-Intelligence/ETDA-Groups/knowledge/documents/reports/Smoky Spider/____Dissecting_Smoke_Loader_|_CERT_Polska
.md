# Reference for threat actor for "Smoky Spider"

**Title**:     Dissecting Smoke Loader | CERT Polska


**Source**: https://www.cert.pl/en/news/single/dissecting-smoke-loader/

## Content






    Dissecting Smoke Loader | CERT Polska

























Report an incident


Back







You're in the menu
About us
                    
About us
About our team
Contact


News
For experts
                    
For experts
News
Publications
Projects
n6
Artemis
MWDB
CVD program
CVD policy
Advisories












About us
News
For experts




Report an incident




About us

About our team
Contact



Baza wiedzy

Fałszywe inwestycje
Uważaj na fałszywe sklepy online
(Nie)bezpieczne płatności
Fałszywi konsultanci
Zadbaj o bezpieczne hasła i logowanie
Fałszywe załączniki w mailach
Fałszywe prośby o szybki przelew
Fałszywe SMSy - plaga ostatnich miesięcy

Biuletyn OUCH!

Porady bezpieczeństwa OUCH!





For experts

Publications



Projects

n6
Artemis
MWDB



CVD program

CVD policy
Advisories











    Dissecting Smoke Loader
                

    18 July 2018
 |         Michał Praszmo |         #analysis,         #malware,         #smokeloader 














Smoke Loader (also known as Dofoil) is a relatively small, modular bot that is mainly used to drop various malware families.
Even though it’s designed to drop other malware, it has some pretty hefty malware-like capabilities on its own.
Despite being quite old, it’s still going strong, recently being dropped from RigEK and MalSpam campaigns.
In this article we’ll see how Smoke Loader unpacks itself and interacts with the C2 server.
 

Smoke Loader first surfaced in June 2011 when it was advertiesed for sale on grabberz.com1 and xaker.name2 by a user called SmokeLdr.


Smoke Loader being sold on grabberz.com 
What’s interesting is that Smoke Loader is sold only to Russian-language speakers3.
Since all functionalities are clearly described in the mentioned forum posts up to 2016 there is no point in listing them all here.
The sample we’ll be analysing is d32834d4b087ead2e7a2817db67ba8ca.


Diagram presenting the unpacking timeline
If you’re only interested in the final payload you can take a quick glance at the diagram above and skip to the final layer.
Table of contents


Layer I
Layer II

Debugger checks:
Lots of garbage code
RC4-encrypted imports:
Unpacking


Layer III

Jump chains

Defeating

Attempt I
Attempt II




Debugging checks
Virtualization checks
Function body encryption
Assembly tricks

Assembly Trick I
Assembly Trick II
Assembly Trick III


Custom imports
Unpacking


Layer IV (final)

String encryption
C2 URLs
Packet structure
Program routine


General IOCs
Collected IOCs
References


Layer I
The first thing Smoke Loader hits us with is a simple PECompact2 or UPX compression.

As with many executable compressions, both are pretty easy do decompress using publicly-accessible software:


PECompact being used to decompress the first layer 

 Decompressing UPX-packed sample 
That wasn’t hard, let’s move on.
Layer II


Entry function, which handles the debugging check and performs some useless api calls as a disguise
 
Debugger checks
The PEB structure is checked against some debugging challenges:

Lots of garbage code
Almost every function is injected with pointless instructions in order to make the disassembly more complicated than it really is.


A part of RC4 function, which contains a lot of useless code
 
RC4-encrypted imports
In this stage, almost all imports and library names are encrypted with RC4 before being passed to LoadLibraryA and then to GetProcAddress.
The encrypted imports are first placed on stack:

Then they are decrypted using RC4 with the hardcoded key:

Finally, the library name is passed to LoadLibrary and the function name to GetProcAddress:

A custom import table is populated this way and used further in execution.
 
Unpacking
Finally, a new process is created and two calls to WriteProcessMemory are performed:

 The writes are pretty characteristic and can be easily noticed in the Cuckoo report 
One of them writes the MZ header and the other rest of the binary. If we concatenate these two writes we’ll get the next layer.
 
Layer III
We’re welcomed with:



 The exported start address 
Well, that’s not good.
What we see is a result of several obfuscation methods and tricks, We’ll look at each one and try to understand how it works.
 
Jump chains
Almost all early-executed functions adapt a chained jumps obfuscation technique.
Instead of placing the instructions in a normal, linear manner, instructions are mixed within the functions with jump instructions connecting consecutive instructions.


The control flow is all over the place 
If we were to write a script to follow the program’s flow and graph instructions we’d probably get something like this:


Partially deobufscated start function 
One can almost immediately see that a vast majority of instructions are used only to divert the natural program flow.
 
Defeating
 
Attempt I
We tried creating an idaapi script that looks through all instruction blocks within a function and tries to concat blocks that are connected with each other via a 1:1 jump (jump from one possible address to one possible location).
The author had probably thought about that and implemented jmp instructions using consecutive jnz and jz instructions. This doesn’t complicate our solution too much though.

 A very naive Python script implementing the mentioned approach 
If we run it on the start function and strip the jumps we get:

A lot better! But we can actually do even better by letting IDA do most of the work for us.
 
Attempt II
The only thing we need to do in order to make IDA recognize these blocks as a valid function is to make sure that all of the jumps are marked as a definitive change of flow control.
While jmp instructions are marked as such by default, the jz/jnz instructions need to by patched to jmp instructions:


Notice the newly-created dotted line that denotes an end of function code 
This trick allows IDA to recognize function bodies and even attempt to decompile them:

 Decompiled start function after patching all jn/jnz instructions 
While (as almost always) the decompilation isn’t 100% correct, it gives us a good basic idea what the function does.
This function, for example, loads the PEB structure and then accessess the OSMajorVersion and BeingDebugged fields.
 
Debugging checks
In this layer, we’ve noticed 2 debugging checks, conveniently located right at the beginning of execution. While they are the same as in the previous stage the approach differs slightly.
What is interesting is that the debugging checks values are used in calculating the next functions addresses:

 Reading the BeingDebugged field from PEB 

 Reading the NtGlobalFlag field from PEB 
The code calculates the next jump address based on the values of BeingDebugged and NtGlobalFlag fields, if either one is not equal to 0 the execution jumps to a random invalid place in memory, harsh.
Normally patching the binary or changing the values mid-debugging works though.
 
Virtualization checks
Binary tries to get the module handle of “sbiedll” (a library that is used in sandboxing processes in Sandboxie) using GetModuleHandleA, if it succeds and thus Sandboxie is installed on the system, the program exits.
A registry key System\CurrentControlSet\Services\Disk\Enum is checked and if any of the following values are found within the string, the program exits.


qemu
virtio
vmware
vbox
xen


Function body encryption
A vast majority of functions are encrypted:

 A function that is partially encrypted 
After deobufscation the encryption function turns out to be pretty simple:

 Decompiled code decryption method 
It accepts an address and number of bytes in eax and ecx registers respectively and xors all bytes in that range with a hardcoded byte.
What’s also interesting is that the binary tries to keep as little code unencrypted at a time as possible:

 Example of keeping the code encrypted 
We’re able to decrypt the chunks using an idaapi patching script:

 Simple idaapi script that xors a given region with a byte 
 
Assembly tricks
This layer employs a few neat position-independent-code assembly tricks.
 
Assembly Trick I





call loc_4024A7 puts the next instructions (in this case string “kernel32”) address onto stack and jumps over the data to the code
pop esi puts the string’s address into esi register
cmp byte ptr [esi], 0 the pointer can be now used as a normal rdata string


 
Assembly Trick II



Instead of executing jmp eax, eax is firstly pushed onto stack and then retn is executed.
 
Assembly Trick III



call $+5 jumps to the next instruction (as call $+5 instruction lengths is 5) but because it’s a call it also pushes the address onto stack.
In this case this is used to calculate the program’s base address (0x004023AA – 0x23AA)
 
Custom imports
This stage uses a custom import table using a djb2 hash lookup.
It first iterates over 4 hardcoded library names, loads each one using LdrLoadDll and stores the handle.



Next, it iterates over 4 corresponding import hashes arrays and looks for matching values.
When a match is found, it grabs the functions address from the library thunk and stores it in an api table that is stored on the stack.


Hashes of functions to be imported 


Constructed api function table 
 
Unpacking
Finally, the program uses RtlDecompressBuffer with COMPRESSION_FORMAT_LZNT1 to decompress the buffer and execute the final payload using PROPagate injection4.

 
Layer IV (final)
 
String encryption
All strings are encrypted using RC4 with a hardcoded key:

 Function used to get a decrypted string from a specific index in the encrypted blob 


Structure of encrypted strings blob 
In this sample, the buffer decrypts to:

 Decrypted strings 
 
C2 URLs
C2 URLs are stored encrypted in the data section:


Part of data section that contains the encrypted URLs 
The encrypted URL structure can be represented as:


Encrypted C2 URL structure 
The encryption method is a simple xor routine with the byte key being derived from the dword key:

 Decompiled function used to decrypt C2 URLs 
Which can be rewritten to Python as:


 Output example 
 
Packet structure

 Decompiled function used to pack and send command packets 
Which can be represented as a C structure:

 A struct representing the structure of command packet 
Packet encryption is done using RC4 yet again. It’s worth nothing, however, that different keys are used for encrypting the outbound packets and decrypting the inbound ones:


A part of decompiled function responsible for encrypting packets before sending them to the C2 


A part of decompiled function responsible for decrypting packets before parsing them 
 
Program routine


The binary starts by obtaining a User Agent for IE version acquired by querying registry key Software\Microsoft\Internet Explorer and values svcVersion and Version. The obtained User Agent is used in later HTTP requests.
Next, it tries to connect continuously to http://www.msftncsi.com/ncsi.txt until it gets a response, this way it makes sure that the machine is connected to the internet.
Finallly, Smoke Loader begins its communication routine by sending a 10001 packet to the C&C. It gets a response with a list of plugins to be installed and a number of tasks to be fetched.
The bot iterates over the task range and tries to get each task by sending a 10002 packet with the task number as an argument.
The tasks payload is often not hosted on the C&C server but on a different host and a Location header with the real binary URL is returned instead.
Upon execution of the task, a 10003 packet is sent back with arg_1 equal to task number and arg_2 equal to 1 if the task executed succesfully.




Graph representation of the communication between bot and C2 
 
General IOCs


Program dumps itself to %APPDATA%\Microsoft\Windows\[a-z]{8}\[a-z]{8}.exe
Program creates a shortcut to itself in %APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup\[a-z]{8}.lnk
Performs a System\CurrentControlSet\Services\Disk\Enum\0 registry query
GET requests to http://www.msftncsi.com/ncsi.txt
POST requests with HTTP 404 responses that include data


Example request and response:



Yara rule:

 
Collected IOCs
Malware configs:

Hashes:

 
References
1 https://grabberz.com/showthread.php?t=29680
2 https://web.archive.org/web/20160419010008/http://xaker.name/threads/22008/
3 http://stopmalvertising.com/rootkits/analysis-of-smoke-loader.html
4 http://www.hexacorn.com/blog/2017/10/26/propagate-a-new-code-injection-trick/
https://blog.malwarebytes.com/threat-analysis/2016/08/smoke-loader-downloader-with-a-smokescreen-still-alive/














                            Share:

                            













The CERT Polska team operates within the structures of NASK (Research and Academic Computer
                            Network) —
                            a research institute which conducts scientific studies, operates the national .pl domain
                            registry
                            and provides advanced IT services.


Social media
Facebook
Twitter
GitHub


Contact

                            ul. Kolska 12, PL-01-045 Warsaw, Poland
                            tel.: +48 22 380 82 74
                            fax: +48 22 380 83 99
                            ePUAP: /NASK-Instytut/SkrytkaESP

                            E-mail: [email protected]
                            Incidents: [email protected]












© 2024 NASK
Privacy policy
CSIRT GOV
CSIRT MON






