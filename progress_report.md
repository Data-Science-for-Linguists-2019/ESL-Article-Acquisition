Elena Cimino, e.cimino@pitt.edu

# Progress Reports

### 0: INITIAL COMMIT
Repository created, corpora have been accessed. The first report on progress will be available February 21. By then, I hope to have wrangled the BALC corpus.

## 1: PROGRESS REPORT 1 (2019.02.21 // February 21, 2019)
### Summary:
All of my initial work can be found in my [exploratory_analysis folder](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/tree/master/exploratory-analysis).

I [investigated the BALC corpus](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/exploring_balc.ipynb) to look at the number of files, breakdown of (perceived) proficiency/quality levels, and any issues I might run into. This process helped me decide what files I would investigate (CEPA - the only files with a proficiency rating), where I would get them (total/), how to find the correct version for repeated files, and what issues (concerning coding and formatting) that I might encounter reading in and cleaning the files.

I then proceeded to initiate [acquiring and cleaning the data](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/BALC_clean.ipynb). I targeted CEPA files, which have text and rating for (perceived) proficiency/quality of the text. Files were read into a DataFrame. Essays underwent cleaning, tokenizing, and some preliminary descriptive and quantitative analysis was done.

### Sharing options:
The corpus is publicly available for free download (see below), though no licensing information is available on the webpage or within the corpus documentation. I reached out to one of the corpus compilers, Dr. Mick Randall, and was told that the British University in Dubai (BuiD) would be happy for me to use the corpus for the purpose of this project.

I think I can provide a few samples of the data, so I'll pick a few texts and images for each level to put in a data sample folder (NOT DONE YET AS OF 11:00 AM 2019.02.21!).

### Links:
- [BuiD Arabic Learner Corpus](http://www.buid.ac.ae/balc) (webpage with information on corpus and download link)
- [exploring_balc](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/exploring_balc.ipynb) (exploration phase)
- [duplicated_files](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/duplicated_files.pickle) (pickle file from exploring_balc)
- [clean_files](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/clean_files.pickle) (pickle file from exploring_balc)
- [BALC_clean](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/BALC_clean.ipynb) (acquiring & cleaning, focusing on CEPA files)
