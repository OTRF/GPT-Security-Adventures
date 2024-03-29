# Reference for threat actor for "Andromeda Spider"

**Title**: Andromeda under the microscope

**Source**: https://blog.avast.com/andromeda-under-the-microscope

## Content

































Andromeda under the microscope







































45954095987
Threat Intelligence Team
6-04-2016












Skip to main content
>Close




For home
For home
Products for PC and mobile phone protection


For business
For business
Protect your business with Avast


For partners
For partners
Partner with Avast and boost your business




About us
About us
Careers, investors, media, contact


Blogs
Academy, Blog, Decoded, Forum


Worldwide (English)




For home


Security







Free Antivirus













Basic protection for all your devices





Free Antivirus













Basic protection for all your devices





Free Antivirus













Basic protection for all your devices





Free Antivirus













Basic protection for all your devices







Premium Security













Complete protection against all internet
                                            threats







Ultimate













Our best security, privacy, and performance apps in
                                            one package



Looking for a product for your device? Free Antivirus for PC, Free Security for Android, Free Security for Mac, Free Security for iPhone/iPad


Looking for a product for your device?

Free Antivirus for PC
Free Security for Mac
Free Security for Android
Free Security for iPhone/iPad





Privacy







SecureLine VPN













Encrypt your connection to stay safe on public
                                            networks







AntiTrack













Disguise your digital fingerprint to avoid
                                            personalized ads







Secure Browser













Enjoy safer browsing that’s up to 4x faster







BreachGuard













Protect your personal info from being exposed and
                                            sold






Performance







Cleanup Premium













Boost your computer’s speed and performance





Cleanup Premium













Boost your computer’s speed and performance





Cleanup Premium













Boost your computer’s speed and performance





Cleanup Premium













Boost your computer’s speed and performance







Driver Updater













Automatically update drivers with a single
                                            click







Battery Saver













Maximize your battery life 









                                Store
                            








                                Home
                            







                                Support
                            






                                Store
                            







                                Account
                            




For business


Solutions






Endpoint Protection
                                    















Small Businesses
11-100

Safeguard your data, devices, and apps with Next-Gen
                                            Antivirus, Patch Management,
                                        and Cloud
                                            Backup.





All-In-One Protection
                                    















Medium and Large Businesses
101-1000+


Endpoint
                                            Protection
Backup and
                                            Recovery
Endpoint
                                            Optimization
Cloud Network
                                            Security
Business Hub Security
                                            Platform






Advanced All-In-One Protection
                                    















Channel Partners
MSPs, Resellers, Distributors


Endpoint
                                            Protection
Cloud Network
                                            Security
CloudCare Security
                                            Platform



Not sure which solution is right for your business? Help me choose



Business partners



Become a partner


MSP partners


Reseller partners


Distributor partners


Affiliates


Partner locator





Resources


Trials





                                Store
                            








                                Home
                            






                                Contact sales
                            







                                Support
                            





                                Store

                            







                            Account
                        


Business Hub
CloudCare
Reseller portal






For partners


Smart Life


Mobile Security


VPN


Threat Intelligence


Knowledge Center




About us


About Avast


Careers


Privacy





Privacy


Expert guides


Privacy blogs







Blog





Avast News



Business Security



Covid-19 Scams



Diversity & Inclusion



Elders



Privacy



Sandwich Generation



Security News



Threat Research



Tips & Advice








Press center





Press releases


Events


In the news


Media materials


PR contacts







Investors



Our story


At a glance


Strategy


Technology
                                                expertise


Leadership


History




Investors


Overview


Growth &
                                                competitive advantage


IPO information


Regulatory news


Share price &
                                                tools


Corporate
                                                governance


Investor contacts


Financial
                                                calendar


Results, reports
                                                & presentations

Analyst consensus


Shareholder
                                                information


Contact us









Awards


Diversity & Inclusion





Diversity & Inclusion


Accessibility







Contact us




Blogs


Avast Blog
Read about recent news from the security world




Avast Academy
Expert tips and guides about digital security and
                            privacy




Avast Decoded
In-depth technical articles regarding security
                            threats




Avast Forum
Discuss with the community







 
List of available regions


Main regions

Worldwide (English)
Europe (English)
América Latina (español)




AMERICAS


Argentina
Brasil
Canada (English)
Canada (français)
Chile
Colombia
EE.UU. (español)
México
USA (English)


América Latina (español)




EUROPE, MIDDLE EAST & AFRICA


België (Nederlands)
Belgique (français)
Česká republika
Danmark
Deutschland 
España
France
Italia 
Magyarország
Nederland
Norge
Polska
Portugal
Schweiz (Deutsch)
Slovensko (česky)
South Africa


Suisse (français)
Suomi
Sverige
Türkiye
United Arab Emirates
United Kingdom
Ελλάδα
ישראל
Казахстан
România
Россия
Україна
                            (українська)
Украина
                            (русский)
المملكة العربية السعودية

الدول العربية


Europe (English)




ASIA & PACIFIC


Australia
India
इंडिया (हिंदी)
Indonesia (English)
Indonesia (Bahasa
                            Indonesia)
Malaysia (English)
Malaysia (Bahasa Melayu)

New Zealand
Philippines (English)
Pilipinas (Filipino)


Singapore
Việt Nam
日本語 
대한민국
简体中文
繁體中文
ประเทศไทย


Worldwide (English)









Close
Sections

All
business security 
Avast News 
Security News 
Tips & Advice 
Viewpoints 
Privacy 
Threat Research 
Diversity & Inclusion 
Diversity & Inclusion 

Blog Authors
Visit Avast website
Change language

English
Deutsch
Čeština
Español
Français
Polski
Português
Русский
日本語











Avast Blog






Andromeda under the microscope









Andromeda under the microscope








Threat Intelligence Team  6 Apr 2016






Andromeda is one of the longest running and most prevalent malware families to have existed.
Andromeda is one of the longest running and most prevalent malware families to have existed. Andromeda was first discovered in late 2011 and it probably evolved from ngrBot/DorkBot. Throughout its existence, the groups behind Andromeda have used various methods to spread the malware and infect users.
We have seen Andromeda spread via spam email campaigns with infected files attached (doc, xls, pdf, zip.), through illegal download sites, warez (infected cracks, keygens, ..), or infecting users via other phishing campaigns.
Infection vector
In recent months, the authors have mainly focused on spreading Andromeda via exploit kits (Neutrino, Nuclear, Angler,..) located on compromised websites or advertisement services. These exploit kits are mainly found on a dubious sites (p0rn, warez, video streaming sites, share sites etc.) but occasionally appear on trusted sites as well.

Andromeda binary files are almost always stored on hacked websites, but we have also discovered files hosted on a few dedicated servers that only host malware. Not only have we seen Andromeda appear on hacked websites, but we have also seen its plugins being distributed on SourceForge.net, a repository that hosts 7zip, VLC player, OpenOffice, FileZilla and other popular open source projects.
Andromeda’s core anatomy
This analysis covers the latest variant of Andromeda samples, which began spreading since the beginning of this year. The authors have not made many changes to Andromeda’s core binary file, but  they are constantly changing the PE packer/obfuscator in the top most layer. Andromeda uses various PE packers of different quality to avoid AV detections. Some packers also contain other anti-vm/emul/debug tricks. We’ve seen a packer very similar to Zbot (based on its source code), obfuscated Visual Basic and .NET binaries and even a few custom packers reminiscent of Dridex included in the Andromeda variant.
Andromeda’s authors put a lot of effort into diversifying their portfolio of infection droppers and to disable, or at least complicate the sample submission and exchange between AV companies and their regular process used to scan and thoroughly analyze files. To achieve this, they update the custom packers daily and as a bonus, they bloat the binaries with more than 70 MB of garbage. This strategy can either significantly prolong the sample upload (on a slow connection) or cause an overflow of scan/submit limits of some antivirus scanning engines (or online scanning services respectively). On the other hand, this trick is suspicious and it can help to heuristically detect the file.
Zbot-like packer in detail
Andromeda’s top-layer packer is interesting and deserves a closer look. The packer is very similar to that of Zbot, based on the source code. The encrypted payload is stored inside the “.rsrc” section as the “raw data”.

The Andromeda payload is twice encrypted with custom encryption and compressed by the RtlCompressBuffer API function with LZ compression (0x002 - COMPRESSION_FORMAT_LZNT1). The custom encryption uses random seed values and generic obfuscation with lots of SMC (self-modificated code) and junk instructions.
First payload custom encryption:

Second encryption:

The decrypted data is then ready for a decompression via the significant RtlDecompressBuffer API function.

Payload Loader
Under all of the obfuscated layers, we found a typical Andromeda payload loader binary. The entire loader is very minimalistic (~20kB) and includes the final malware payload in compressed (Aplib) and encrypted (RC4) form and hardcoded config structure.
Loader config structure
The structure is hardcoded right before the encrypted payload that is 0x28h (40) bytes long and it contains seven values: 

RC4 key for payload decryption (first 16 bytes).
Payload size (dword).
Payload CRC32 hash (dword).
Heap allocation size for decompressed payload data (dword).
Entry point of decompressed payload (dword).
Pointer to decompressed payload data section (dword).
Size of decompressed payload data section (dword). This value is unused by loader.


Entire config structure is located at the beginning of  “.rdata” section (VA offset: 0x00402000h).
Loader API hashes
It’s interesting that Andromeda’s loader binary has no imports (in PE directories). The payload loader uses only the ntdll.dll library and all imported API functions are hardcoded as custom hash values.
The malware obtains a handle of the ntdll.dll library via a PEB_LDR_DATA (contains the base address of ntdll and kernel32) trick, well known from many shellcodes:

Hashing algorithm is trivial and combines XOR and ROL operations over API names (ASCII). 

All API hashes are stored at the beginning of “.text” section (VA offset 0x00401000h) as DWORD values.

The authors seem to be very experienced native subsystem and low-level programmers and have deep knowledge of the AV detection methods. This malware uses very uncommon API functions in low-level form (Nt/Rtl), which is probably used to avoid standard API monitors/tracers, sandboxes and other dynamic analysis tools with predefined API lists or well known API combinations patterns.
List of all hashes and resolved API functions:




Hash value


API function




0AB48C65 


LdrLoadDll




DE604C6A 


RtlDosPathNameToNtPathName_U




925F5D71 


RtlFreeAnsiString




EFD32EF6 


LdrProcessRelocationBlock




B8E06C7D 


RtlComputeCrc32




831D0FAA 


RtlExitUserThread




A62BF608 


NtSetInformationProcess




102DE0D9 


NtAllocateVirtualMemory




7CD8E53D 


NtFreeVirtualMemory




6815415A 


NtOpenFile




E7F9919F 


NtQueryDirectoryFile




64C4ACE4 


NtClose




028C54D3 


memcpy




82D84ED3 


memset




Payload encryption & compression
The final Andromeda payload is compressed with Aplib and encrypted with RC4 stream cipher. The encrypted payload is verified with a hardcoded CRC32 hash and proceeds to decryption if this check passes.

RC4 decryption followed by Aplib decompression:

Final payload fixups
Once the payload is decrypted and unpacked, it’s necessary to relocate it to its new base address, because it is not a position independent code. This is done through another uncommon API call - LdrProcessRelocationBlock - which is a function used only internally by the system to relocate loaded PE modules.

The API function takes a pointer to a relocation record and information about the old and new base address. First relocation record is stored at the beginning of payload data section.

After processing each relocation record, the LdrProcessRelocationBlock function returns a pointer to the next record. This makes it possible to traverse to the end of relocations (there’s a terminating null, which signals that there’s nothing else to process).
The last step in the loader part is the API function preparation for the final Andromeda payload. All API functions are represented by the same custom hash form (XOR+ROL) described earlier.
There is also a little config structure located right after the relocation records. The first value of this structure is a custom hash (DWORD) of the DLL file name. The second value is offset to the final payload (DWORD), where resolved API functions will be stored.  The custom hashes (DWORD) of API functions from DLL terminated with 0x0000h are also stored.

The algorithm for resolving the DLL file name from the hash is similar to resolving API hashes, but it also contains lower-case transformation.

The loader uses a very uncommon method to search and load resolved DLL files. All steps are made through low-level API and the authors use the same method with PEB_LDR_DATA structure as described above. The loader uses returned UNICODE string from the FullDllName value this time.

This unicode string with the full DLL path is used as an argument for the RtlDosPathNameToNtPathName_U API function, which transforms the unicode file path string into following unicode format:
“\??\C:\WINDOWS\system32\ntdll.dll"
This string is used to extract the fully qualified path and the “*.dll” file mask and pass them to the NtQueryDirectoryFile API function, which then enumerates libraries in the system directory. Each library name is hashed and compared with stored custom hashes. If the hashes are equal, the DLL file is directly loaded via the LdrLoadDll API function and the loader continues to resolve API function names from hard-coded hashes.
Finally, the loader writes all the resolved function pointers to the payload. The payload itself uses a more sophisticated API redirection method, which first copies an instruction from the particular API function to the final payload, then executes it and redirects back to the original API function’s second instruction. This technique is known as stolen bytes. The authors use JMP instructions 0xEB and 0xE9 for this trick.

Example of the API redirection:

These mangled calls of API functions made  our analysis harder, because the debugger cannot correctly identify/resolve the names of the API functions when they are called this way.
List of all used API functions inside final payload:




ntdll.dll


isdigit, memcpy, memset, NtDelayExecution, NtMapViewOfSection, NtQueryInformationProcess, NtQuerySection, NtUnmapViewOfSection, pow, RtlComputeCrc32, RtlImageHeader, RtlRandom, RtlWalkHeap, _allmul, _alloca_probe




ws2_32.dll


closesocket, connect, FreeAddrInfoW, getaddrinfo, getsockname, htonl, ioctlsocket, recv, sendto, socket, WSACloseEvent, WSACreateEvent, WSAEventSelect, WSAStartup




kernel32.dll 


CloseHandle, CopyFileW, CreateEventW, CreateFileMappingA, CreateFileW, CreateProcessW, CreateThread, CreateToolhelp32Snapshot, DeleteFileW, ExitProcess, ExitThread, ExpandEnvironmentStringsW, FlushInstructionCache, FreeLibrary, GetCurrentProcess, GetEnvironmentVariableW, GetFileTime, GetModuleFileNameW, GetModuleHandleA, GetModuleHandleW, GetProcAddress, GetProcessHeap, GetSystemTimeAsFileTime, GetThreadContext, GetTickCount, GetVersionExW, GetVolumeInformationW, GetWindowsDirectoryW, GlobalAlloc, GlobalFree, GlobalLock, GlobalReAlloc, GlobalSize, GlobalUnlock, HeapDestroy, LoadLibraryA, LoadLibraryW, LocalFree, lstrcatW, lstrcmpiW, lstrcpy, lstrcpyW, lstrlen, lstrlenW, MapViewOfFile, Module32FirstW, Module32NextW, MoveFileExW, MultiByteToWideChar, NTDLL.RtlAllocateHeap, NTDLL.RtlFreeHeap, NTDLL.RtlGetLastWin32Error, NTDLL.RtlSizeHeap, OpenEvenW, Process32First, Process32Next, QueueUserAPC, ResumeThread, SetEnvironmentVariableW, SetErrorMode, SetEvent, SetFileAttributesW, SetFileTime, Sleep, TerminateProcess, UnmapViewOfFile, VirtualAlloc, VirtualFree, VirtualProtect, WaitForSingleObject, WriteFile




advapi32.dll


AdjustTokenPrivileges, CheckTockenMembership, ConvertStringSecurityDescriptorToSecurityDescriptorA, ConvertStringSidToSidA, GetSidSubAuthority, GetSidSubAuthorityCount, GetTokenInformation, LookupPrivilegeValueA, OpenProcessToken, RedEnumValueW, RegCloseKey, RegCreateKeyExW, RegDeleteValueW, RegFlushKey, RegOpenKeyExW, RegQueryValueExW, RegSetKeySecurity, RegSetValueExW




user32.dll


FindWindowA, GetKeyboardLayoutList, mouse_event, SendMessageA, wsprintfA, wsprintfW




shell32.dll


ShellExecuteExW




ole32.dll


CoInitialize, CreateStreamOnHGlobal




winhttp.dll


WinHttpCloseHandle, WinHttpConnect, WinHttpCrackUrl, WinHttpOpen, WinHttpOpenRequest, WinHttpQueryHeaders, WinHttpReadData, WinHttpRecieveResponse, WinHttpSendRequest, WinHttpSetOption




dnsapi.dll


DnsExtractRecordsFromMessage_W, DnsFree, DnsWriteQuestionToBuffer_W




shlwapi.dll


PathFindFileNameW, PathQuoteSpacesW, PathRemoveBackslashW, PathRemoveFileSpecsW, StrChrW, StrRChrW, StrToIntW





 As you can see, the authors use many uncommon or undocumented API functions.
There are some special cases matched by RegEx, where the authors use NTDLL.Rtl functions from the kernel32.dll library and the Andromeda loader had to load the ntdll.dll again and use proper pointers for the Rtl API functions.

After resolving all hard-coded DLLs and API functions, the loader continues to final payload Entry Point.
 

Final Andromeda payload
Although the final payload is very small (~24 kb), the code is very complex and sophisticated. The authors, again, use a variety of anti-emul and anti-vm tricks.
At the very beginning, Andromeda disables Windows error notifications via the SetErrorMode API function with 0x8007h parameter, which means SEM_FAILCRITICALERRORS, SEM_NOALIGNMENTFAULTEXCEPT, SEM_NOGPFAULTERRORBOX, SEM_NOOPENFILEERRORBOX.

Anti-VirtualMachine protection
Andromeda uses a simple and well-known anti-vm trick that compares the names of running processes with a “black list” of prohibited process names stored as CRC32 hashes.
List of forbidden process names:





99DD4432 


vmwareuser.exe  




2D859DB4 


vmwareservice.exe 




64340DCE 


vboxservice.exe  




63C54474 


vboxtray.exe  




349C9C8B 


sandboxiedcomlaunch.exe 




3446EBCE 


sandboxierpcss.exe  




5BA9B1FE 


procmon.exe




3CE2BEF3 


regmon.exe  




3D46F02B 


filemon.exe 




77AE10F7 


wireshark.exe 




0F344E95D 


netmon.exe  




2DBE6D6F 


prl_tools_service.exe




0A3D10244 


prl_tools.exe




1D72ED91 


prl_cc.exe




96936BBE 


sharedintapp.exe




278CDF58 


vmtoolsd.exe  




3BFFF885 


vmsrvc.exe  




6D3323D9 


vmusrvc.exe  




0D2EFC6C4 


python.exe




0DE1BACD2 


perl.exe 




3044F7D4 


avpui.exe





 
This procedure is implemented through the classic API functions, CreateToolhelp32Snapshot and Process32First / Process32Next. If the malware reveals a forbidden running process, the execution flow ends in an infinite loop.

An interesting feature is the possibility of creating a special key in the registry, which allows Andromeda to infect the system even with a running blacklisted processes. 
The process blacklisting functionality is ignored when “is_not_vm” key is present inside the "HKEY_LOCAL_MACHINE \ SOFTWARE \ Policies" registry and when the proper UserID (DWORD) is set.

Persistence
The techniques to persist the infection and to camouflage the Andromeda PE binary among regular system binaries are well designed. All communication goes through an injected system application - msiexec.exe, which is a part of the standard Windows Installer.
Andromeda copies itself to the %ALLUSERPROFILE% folder and renames the binary to "ms {random [az] {5}}.exe” where the UserID is used as a seed for the RtlRandom API function.

Later, the resulting file’s attributes are set to “FILE_ATTRIBUTE_HIDDEN” and “FILE_ATTRIBUTE_SYSTEM” (+h +s) and the file time is set to the file time obtained from the original msiexec.exe file. The well known functions - GetFileTime and SetFileTime are used.

Another trick used by the authors is deleting the NTFS stream bound to the file. They call the DeleteFile API to remove the :Zone.Identifier flag from the newly created ms*.exe file (to bypass the “File Downloaded from the Internet” warning).

In the next step, Andromeda prevents the displaying of hidden files via the registry key "Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" and sets proper “Hidden” and “ShowSuperHidden” values.

Finally, Andromeda creates a new value (UserID) inside the “Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\Run” registry key and sets the path to the previously created “ms*.exe” file. After that, it protects the value by changing the permissions through Security Descriptors. Andromeda tries to avoid modifications or deleting of this value, however, modern AV engines are able to bypass this restriction.


 
Injection of msiexec.exe and system API function hooks
The entire final payload is injected to a newly created msiexec.exe process and activated via the ResumeThread API function. The original payload process is terminated after a new thread activation and the malware only continues from the injected msiexec.exe process.

Andromeda also injects ntdll.dll and ws2_32.dll system libraries. Inside ntdll.dll Andromeda hooks the NtMapViewOfSection API function and replaces it with a jump to payload, and  also hooks the GetAddrInfoW API function inside the ws2_32.dll library.


Both API hooks are resolved inside the payload and then jump to the affected API functions after being replaced by jmp instructions.
Part of the resolved code for the GetAddrInfoW API function by payload:

Language exclusions
Another interesting feature is the detection of keyboard layout settings. If Andromeda detects the Russian, Ukrainian, Belarusian or Kazakh keyboard, it sets a special flag that disables the infection, persistence, NTP traffic and injection of ntdll and ws2_32 libraries.

The malware is also completely removed from the infected machine if it detects one of these keyboard layouts.
NTP traffic
Andromeda uses hardcoded NTP (Network Time Protocol) domains to obtain the current time, which is  received by the “Transmit Timestamp”, if this connection isn’t successful the current time is obtained from infected computer.

The hardcoded NTP domains are africa.pool.ntp.org, asia.pool.ntp.org, europe.pool.ntp.org, oceania.pool.ntp.org and pool.ntp.org as the last attempt if the other domains fail. NTP traffic uses port 123.
The malware verifies if the size of the received data is 0x30h (48) bytes and first parses DWORD from the “Transmit Timestamp” value. 

This value is increased by 0x7C558180h and the result is used as an argument of the “aStart” function exported by a plugin.

If all connections to the NTP domains fail, an argument for the aStart function is computed by the payload via the following algorithm based on the result of the GetSystemTimeAsFileTime API function, instead of the Transmit Timestamp value from the NTP request.

The  “compute_aStart_arg” function algorithm:

Obtain local IP via sockaddr struct
Andromeda uses a very uncommon method to obtain local IP addresses of infected machines.
The malware tries to connect various legal servers on port 80 with a crafted socket and obtain the infected machine’s IP address from the sockaddr structure via the getsockname API function.

The resolved value is used as “la” parameter for C&C requests.
List of domains that  Andromeda tries to connect to in the following order: update.microsoft.com, microsoft.com, bing.com, google.com, yahoo.com
C&C communication
All communication is RC4 encrypted and uses HTTP/1.1 in the raw data format “Content-Type: application/octet-stream” with predefined “Mozilla/4.0” User-Agent.

Andromeda contains a hard-coded RC4 key, which is used for C&C server communication, for the downloaded plugin decryption and also for decrypting hard-coded C&C URLs where the key is used backwards.
All values are hardcoded to a structure located in the beginning of payload data. The first value is BID (Botnet/BuildID), which is also used as a parameter for C&C requests. RC4 key is hard-coded between random junk data and is followed by encrypted C&C URLs. The first byte of each encrypted URL is the length of data and it is used as a pointer to the next encrypted URL. Zero byte indicates the end of an encrypted URL data block.

C&C JSON requests
Andromeda uses JSON format for all communication with C&C servers encrypted with RC4.

The malware includes two types of JSON requests and one command object.
Infection report / Ask for action request
{"id":%lu,"bid":%lu,"os":%lu,"la":%lu,"rg":%lu}





JSON item


Name


Info




id


User ID


Computed from VolumeSerialNumber of infected machine HDD.




bid


Botnet/Build ID


Hard-coded inside Andromeda payload.




os


OS version


Version of current operating system.




la


Local IP address


Obtained from sockaddr structure.




rg


Administrator rights


Set 1 if malware process runs under an administrator account.





 
Live example:
{"id":1839815145,"bid":8384538,"os":65889,"la":168732589,"rg":0}
Received command object from C&C server
[sleep_before_request, {unused_object}, [TaskID, RequestType, URL,..]..]





Object item


Info




sleep_before_request


Sleep time in minutes before send next request to the C&C server, the most common value is 60.




{unused_object}


When this object is found, it is skipped. The most common value is {“klt:0”}.




TaskID


ID of a task provided by the C&C server. This ID is send back to server with status/error report request.




RequestType


Identifier of the task type (update plugin, download exe, install plugin, delete bot)




URL


URL for downloading plugin or other malware.





 
Live example of a command to download Andromeda plugins:
[60,{"klt":0},[15,2,"http:\/\/netcologne.dl.sourceforge.net\/project\/googlecodefork\/g11.pack"]]
Task report request
{“id”:%lu, “tid”:%lu, “err”:%lu, “w32”:%lu}




JSON item


Name


Info




id


User ID


Computed from VolumeSerialNumber of infected machine HDD.




tid


TaskID


ID of task provided by the C&C server.




err


Error


Set 0 if task is successfully completed.




w32


System error code


Obtained from RtlGetLastWin32Error API function.





 Live example:
{"id":1839815145,"tid":15,"err":0,"w32":127}
C&C servers
The Andromeda payload uses two domains as C&C servers for a very long time period and requests are sent via POST method.
Server one:
hxxp://disorderstatus.ru/order.php
Server two:
hxxp://differentia.ru/diff.php
Both domains are connected to multiple DNS servers located throughout the world.
Below is the differentia.ru DNS graph up to the April 2016 hosted on pointhq.com servers:


The above map shows where the servers are located.
List of “A” IP domain records:




IP


Hosted by


Location




46.4.114.61


Hetzner Online GmbH


Germany




95.213.192.71


Selectel Net


Russian Federation




176.9.48.86


Hetzner Online GmbH


Germany





 
The below shows a DNS graph of the differentia.ru domain hosted on Hurricane Electric servers, where the authors currenlty moved the entire network infrastructure.


 
Complete current DNS record of differentia.ru:




NS


ns1.he.net


216.218.130.2


United States CA Fremont Hurricane Electric HURRICANE-1




SOA


ns1.he.net


216.218.130.2

 



NS


ns2.he.net


216.218.131.2

 



NS


ns3.he.net


216.218.132.2

 



NS


ns4.he.net


216.66.1.2


United States CA Fremont Hurricane Electric HURRICANE-6 




NS


ns5.he.net


216.66.80.18

 



A


95.213.186.51

 

Russian Federation SELECTEL-NET SELECTEL OOO "Network of data-centers "S RU-SELECTEL-20090812 




A


176.9.174.220

 

Germany HETZNER-RZ-FKS-BLK4 HETZNER-AS Hetzner Online GmbH DE-HETZNER-20110517 





 
Statistics of blocked differentia.ru domain:


Downloaded plugins includes other C&C server domains:
atomictrivia.ru, designthefuture.ru, gvaq70s7he.ru, getuptateserv.eu,..
Andromeda Plugins
This malware is modular and Andromeda offers several plugins like Keylogger, Browser Formgrabber, Rootkit, Hidden TeamViewer remote control, etc. We are preparing a detailed analysis of the all modules which we will publish at a later date.
The plugins are hosted and downloaded from the Source Forge repository.

The authors recently updated the plugin files, repacked binaries with PE packers and changed their file names. This Source Forge project was registered on 2015-05-16 under “dofeedthetrolls” username.

Plugin encryption
The plugin binaries are twice encrypted with RC4 encryption and compressed by Aplib. Each plugin contains 43 bytes of config header, with a hard-coded RC4 key, CRC32 hashes and data length values for validation and a parameter for the case the plugin is stored in the registry.
Encrypted plugin header:

Decrypted plugin header:

Decrypting the plugin is a bit tricky:

Decrypt header (43 bytes) with a RC4 encryption key from the Andromeda payload (used for C&C communication).
The first DWORD value is the XOR key to decrypt the config header values.
The first 16 bytes are the RC4 key to decrypt the plugin.
Decompress (Aplib) decrypted data.


Plugin persistence
Downloaded plugins are stored in the registry and  in the %TEMP% directory under two file names.
The first file name is saved in the following format: %TEMP%\KB{GetTickCount}.exe

The second file name is %TEMP%\cdo*.dll

The Andromeda payload also searches for three plugin exports aStart, aUpdate and aReport via the GetProcAddress API function.
Conclusion
Andromeda malware has very long history. It’s one of the most prevalent malware families and nothing indicates that it will disappear anytime soon. The authors are skilled programmers and operators, recently updating plugins, maintaining entire systems and looking for new infected domains with Exploit Kits. Analyzing Andromeda's very complex ecosystem is a challenging task, but we're investigating it further. Stay tuned for the next blog post!




























































Related articles










Unzipping the truth: The hidden dangers of .zip domainsThat .zip file looks legit, but it's actually a sneaky new way for cyber criminals to steal your info. 

1 Aug 2023





 min read














Avast reaches out to Ursnif malware victimsInformation belonging to over 100 Italian banks breached by the Ursnif banking trojan was obtained by Avast Threat Labs, which then shared the data with as many of the victims as could be identified. 

5 Mar 2021





 min read














Avast researchers obtain Ursnif victim data: Reach out to help victimsAvast researchers obtained information that the Ursnif banking Trojan has targeted 100 Italian banks and may have thousands of victims.

2 Mar 2021





 min read











Subscribe to our newsletter


Subscribe





Most popular











Video: Accept all cookies? A recipe for online privacy this holiday season
11 Dec 2023

















How to use Discord’s ‘Family Center’ to help protect your child
24 Jul 2023

















The hidden pitfalls of travel apps
13 Jul 2023

















Avast researchers uncover disturbing crowdfunding scheme
28 Jun 2023



















Your essential cybersecurity checklist for safe summer travel
14 Jun 2023


























Never miss our news




Follow us


























1988 - 2024 Copyright © Avast Software s.r.o. | Sitemap Privacy policy

















 -->
       -->
      










































