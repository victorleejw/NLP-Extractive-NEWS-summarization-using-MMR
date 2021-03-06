## Comparison of MMR and LexRank Automatic Text Summarization approaches

[Automatic summarization](https://en.wikipedia.org/wiki/Automatic_summarization) techniques are used to automate the process of summarizing document(s) to form a relatively shorter summary that conveys the most important information from the original larger text. Multi-document summarization in particular is used to extract summary from multiple documents written about the same topic. Here we have to tried to implement and compare two very commonly used techniques for multi-document automatic text summarization:
* [Maximal Marginal Relevance](http://www.cs.cmu.edu/~jgc/publication/The_Use_MMR_Diversity_Based_LTMIR_1998.pdf) (MMR)


* [LexRank](http://www.jair.org/papers/paper1523.html)

#### Implementation details

We have implemented both MMR and LexRank algorithms in python. For evaluation purpose we have used the [DUC2004 data corpus](http://www-nlpir.nist.gov/projects/duc/data/2004_data.html) which contains two sets of documents.
* **Documents/clusters**: contains 50 different topics each containing on average 10 news articles.


* **Manual summaries**: manually created summary for each of the 50 topics.

The generated summaries are evaluated against the human summaries using the [ROUGE](http://www.aclweb.org/anthology/W04-1013) toolkit. The ROUGE scores help to compare the efficiency of the individual summarization systems. However we have also performed an analysis of how much similar (overlap) the summaries generated by each of these systems are by calculating Jaccard coefficient score for sentence level and word level overlap.

#### System/software requirements

We had implemented both MMR and LexRank and ran the evaluations (both ROUGE and Jaccard evaluations) on Ubuntu 14.04. The following packages were installed as part of this on the Ubuntu OS:
* [python 2.7](https://www.python.org/downloads/release/python-2712/)


* [PyRouge version 0.1.0](https://pypi.python.org/pypi/pyrouge/0.1.0)


* [ROUGE toolkit 1.5.5](http://www.berouge.com/Pages/default.aspx)

#### Files and Folders

| Folder						| Description								 |
| :---------------------------: |:------------------------------------------|
| [root](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR)	| root folder of project containing all required files and folders |
| [Documents](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/tree/master/Documents) | news articles relating to the 50 topics (each topic containing 10 articles) |
| [Humman_Summaries](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/tree/master/Human_Summaries/eval) | human summaries used to evaluate the quality of system generated |
| [Lexrank_results](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/tree/master/Lexrank_results) | folder which holds the system generated summaries of LexRank |
| [MMR_results](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/tree/master/MMR_results) | folder which holds the system generated summaries of MMR |
| [LexRank.py](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/blob/master/LexRank.py) | LexRank summarizer implementation |
| [mmr_summarizer.py](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/blob/master/mmr_summarizer.py) | MMR summarizer implementation |
| [sentence.py](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/blob/master/sentence.py) | sentence class for modelling sentences in the document cluster |
| [jaccardScore.py](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/blob/master/jaccardScore.py) | for generating jaccard coefficient at word and sentence level |
| [test_pyrouge.py](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/blob/master/test_pyrouge.py) | for generating the ROUGE scores for the system summaries |


#### How to run:

- For generating the **MMR system summaries** run the [mmr_summarizer.py](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/blob/master/mmr_summarizer.py). The results will be generated in the MMR_results folder.


- For generating the **LexRank system summaries** run the [LexRank.py](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/blob/master/LexRank.py). The results will be generated in the Lexrank_results folder.


- For generating the **ROUGE scores** run the [test_pyrouge.py](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/blob/master/test_pyrouge.py). Results will be displayed on the terminal


- For generating the **Jaccard coefficient scores** run the [jaccardScore.py](https://github.com/vishnu45/NLP-Extractive-NEWS-summarization-using-MMR/blob/master/jaccardScore.py). Both word and sentence level scores will be displayed on the screen

**NOTE**: 

The documents from DUC2004 have not been added here. These documents can be obtained from [here](http://www-nlpir.nist.gov/projects/duc/data/2004_data.html).

This work was done as part of the CAP6640: Natural Language Processing course at UCF in Spring 2016 along with [Amar Nair](https://www.linkedin.com/in/amarnair/) and [Syed Ahmed](https://www.linkedin.com/in/syedhope/).