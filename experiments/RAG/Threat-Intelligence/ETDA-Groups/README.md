# RAG: ETDA Threat Actor Encyclopedia Experiments
This Retrieval Augmented Generation (RAG) experiment explores proof-of-concepts to integrate generative AI with threat intelligence. It contains various Jupyter Notebooks that explore the different topics. Every notebook is documented and has various improvement ideas. The ultimate goal is to support analysts in understanding and assessing threat actors. 

## Threat Actor RAG Experiment
This experiment explores how less controlled threat actor information sources perform for RAG use cases compared to using ATT&CK. It scrapes documents listed in the [ETDA Threat Actor Encyclopedia](https://apt.etda.or.th/cgi-bin/aptgroups.cgi). This database contains over 450 threat actors and provides various hyperlinks to reports about operations and information about these threat actors. See "threat-actor-knowledge-builder.ipynb" and "threat-actor-QA.ipynb" for the experiment.

## Report Summarizer Experiment
The scraped reports vary in quality, length, and consistency. By summarizing them through an LLM we can iron out some of these issues. The summaries can also provide additional input for experimentation with multi vector retrievers. This notebook describes how to loop over the reports and create summaries for reports where we can. 

## Threat Actor Assessment
Organizations want to prioritize their resources through threat intelligence. By assessing threat actors for their threat level to your organization you can look at their TTPs to learn and prepare for. However, threat actor assessment can take a lot of effort through manual work, especially when kept up to date. It is also difficult to be consistent on the analysis through time and different analysts. Generative AI could support this process by assessing reports through some model. By leveraging the [threat box model](https://klrgrz.medium.com/quantifying-threat-actors-with-threat-box-e6b641109b11) this notebook experiments with assessing threat actors through LLMs. 
