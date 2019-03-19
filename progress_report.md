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

I think I can provide a few samples of the data, so I'll pick a few texts and images for each level to put in a data sample folder. One file for each level (1 - 6) has been added to the data_samples folder.

### Links:
- [BuiD Arabic Learner Corpus](http://www.buid.ac.ae/balc) (webpage with information on corpus and download link)
- [exploring_balc](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/exploring_balc.ipynb) (exploration phase)
- [BALC_clean](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/BALC_clean.ipynb) (acquiring & cleaning, focusing on CEPA files)
- [data_samples](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/tree/master/data_samples) (1 sample text from each level of the six proficiency levels for CEPA texts)
- [duplicated_files](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/duplicated_files.pickle) (pickle file from exploring_balc)
- [clean_files](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/clean_files.pickle) (pickle file from exploring_balc)

## 2: PROGRESS REPORT 2 (2019.03.18 // March 18, 2019)
### Summary:
I made updates to the __existing__ [BALC_cean](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/BALC_clean.ipynb) jupyter notebook file, adding lemmatization and part of speech tagging. I  wrote out two .csv files to the private data folder, not pushed my GitHub repository. These csv files contain the top 3000 lemmas from the CEPA files (throwing out pronouns and punctuation) and cepa_df in its entirety. These were not shared in the public repository, as I am still not 100% sure these are shareable in their entirety.

I began a __new__ file, [PELIC_data](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/PELIC_data.ipynb) that singles out the target languages I'm interested in and applies filters that will allow me to compare actual comparable essays between BALC and PELIC (written essays that are between 10 and 400 tokens).

I began a __new__ file, [prep_data_analysis](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/prep_data_analysis.ipynb), that compiles the CEPA lemma list and the PELIC lemma lists in order to find mutual lemmas across corpora. Using this list of mutual lemmas, I picked six count and mass nouns to analyze moving forward. I would like to confer with advisors (and possibly other linguistic researchers) about my natural inclinations toward noun type and choice of targets, so these choices may change in the next few days. I would like to have this finalized by Friday, March 22, 2019.

Moving forward, I want to finalize analysis and pick representative samples of the essays to share along with my analyses. I would like to be able to share the CEPA.csv file if I can, as I think it awards the possibility for interesting analyses about Arabic L1, English L2 acquisition in various subfields (e.g. orthography, acquisition of various word forms or classes, etc.)

### Licensing:
I decided to license my repository under the Creative Commons Attribution Share Alike 4.0 International license. This allows others to share and adapt the work, but requires attribution, non-commerical use, and share alike distribution.

### Links:
- [BALC_clean](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/BALC_clean.ipynb) (acquiring & cleaning, focusing on CEPA files)
- [prep_data_analysis](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/prep_data_analysis.ipynb)
- [PELIC_data](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/PELIC_data.ipynb)
