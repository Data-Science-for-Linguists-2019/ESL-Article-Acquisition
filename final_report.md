# Final Report: ESL Article Acquisition

Elena Cimino
2019.04.26

### Table of Contents

- [1. Project Overview](#1)
  - [1.1. Background information](#back)
  - [1.2. Research process](#process)
  - [1.3. Setbacks and difficulties](#hardships)
- [2. Data](#2)
  - [2.1. BALC](#BALC)
  - [2.2. PELIC](#PELIC)
- [3. Linguistic Analysis](#3)
  - [3.1. Articles in PELIC](#articles)
  - [3.2. Article errors in PELIC](#errors)
  - [3.3. Qualitative analysis of article usage](#usage)
- [4. Conclusion](#4)
  - [4.1. What I learned](#learn)
  - [4.2. Moving forward](#forward)

<a id='1'></a>
## 1. Project overview

<a id='back'></a>
### 1.1. Background information

I have an interest in second language acquisition as well as computational and corpus linguistics. This term, I took both Data Science for Linguists as well as Advanced Second Language Acquisition. I wanted to do a project that would work for both of these subjects and decided to do an investigation into non-native acquisition of English articles, which is a topic I have done a bit of theoretical/background research into in the past. However, while there is much work done on English as a Second Language (ESL) learners with native languages that have definite, indefinite, and zero articles (such as Spanish), and ESL learners with native languages that lack articles (such as Chinese), there is little investigation on the acquisition of English articles by native speakers of Arabic, which has definite and zero articles but lacks indefinite articles.

I knew I was interested in analyzing the Pitt English Language Institute Corpus (PELIC), as it has over 40,000 texts from learners of many different L1s, but I also found a corpus from the British University in Dubai called the BuiD Arabic Learner Corpus (BALC). This has 1,865 texts from native Arabic speakers learning English that I could also analyze.

My questions setting out were:
- What kinds of articles do L2 learners of English have troubles acquiring?
- Is there an L1 effect in the acquisition of non-native English articles?
- How do Arabic L1 speakers acquire articles with reference to other L1s?

<a id='process'></a>
### 1.2. Research process

PELIC had already been largely cleaned up and processed by the time I came around, so much of my cleaning and processing was done on the BALC corpus, initially.

Cleaning BALC texts was an adventure! There were [several different folders](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/exploring_balc.ipynb#background) with the texts I was interested in examining, and there was a bit of [data loss](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/exploring_balc.ipynb#images) in some of the folders. Additionally, [some files](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/exploring_balc.ipynb#repeat) appeared multiple times in different folders or in different levels, so I had to figure out where everything was supposed to go.

I read in my target texts (essays from the Common Education Proficiency Assessment, or CEPA) into a dataframe and then had to [clean](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/BALC_clean.ipynb#clean) the files, which had originally been a huge hurdle. Some of the texts were coded for student corrections, but the coding wasn't always consistent, so sometimes the spacing would be off or tags wouldn't close correctly. I normalized the tagging, and then eventually ['revised'](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/BALC_clean.ipynb#expand) the essays by removing the tagging and cleaning all of the texts up.

I ended up getting information about text length, parts of speech, and lemmas in these essays in BALC, though my analysis in the end was largely based on PELIC. However, I did learn some useful things about cleaning files and double-checking the contents of the corpus through this!

Initially, I was going to do a string search on essays and analyze article usage through that. However, as I [realized later](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/analysis/analysis_1.ipynb), this wasn't the best idea. So I started a more [holistic analysis](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/analysis/analysis_2.ipynb) on the essays as a whole, as well as doing more [quantitative work on PELIC](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/analysis/quantitative_analysis.ipynb#section3) as a whole corpus.

<a id='hardships'></a>
### 1.3. Setbacks and difficulties

As mentioned earlier, some of the coding for BALC was all over the place, and it made it impossible to look at every text in the corpus, since I would solve one coding issue only to create three more. Therefore, I had to make a decision about which essays I was going to use. Also mentioned earlier was deciding how to do a fine-tuned linguistic analysis on article usage in essays. I had lemmatized BALC and compiled a list of the most frequent lemmas to cross-check with the most common lemmas in my target languages in PELIC (Arabic, Spanish, and Korean). However, I had an awful time finding lemmas that occurred in at least one essay in each of my target L1s at every level across the two corpora, and I had to change my list of targets multiple times. Then, I ended up abandoning the idea of the string search altogether, since the target words rarely occurred more than once in the texts.

There's also the fact that, because there are many English article rules that are based on context (e.g. non-count nouns should take the zero article, but they can take _the_ if they are post-modified), and so that kind of analysis has to be done by hand, or at least double-checked by a human. Therefore, my quantitative analysis was concentrated on the [article makeup](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/analysis/quantitative_analysis.ipynb#section3) of PELIC (raw counts, ratios, top 10 most common nouns to follow certain articles, etc.) as well as trying to compute a rather straight-forward rule that can't be violated in English: [plural nouns can't take an indefinite articles](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/analysis/quantitative_analysis.ipynb#erroranalysis).

<a id='2'></a>
## 2. Data

<a id='BALC'></a>
### 2.1. BALC

The BALC corpus can be found [here](http://www.buid.ac.ae/balc). As mentioned earlier, it's a corpus with 1,865 texts from high school seniors and first year college students in Dubai. The corpus is comprised of mostly plaintext files, but there are JPG files that accompany the CEPA texts.

I didn't end up analyzing BALC quantitatively, like I did PELIC, but I ended up processing a little over 1,600 files in the corpus. Texts per level can be seen below.

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/balc_texts_per_level.png)

While I didn't end up doing a lot of quantitative analysis on the CEPA texts, I did end up [tokenizing, POS-tagging, and lemmatizing]((https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/BALC_clean.ipynb#expand) those files.

I also learned about a better measure than type-token ration (TTR) for lexical diversity called Guiraud's R, which better accounts for text length than TTR. For example, below you'll see the text lengths for each level of CEPA essay in BALC.

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/balc_tokcount.png)

This is the TTR spread, in which lower levels (typically shorter) have a higher TTR, since there are fewer words in the text, and that means words are less likely to be repeated.

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/balc_ttr.png)

And this is Guiraud's R, which more closely resembles the text length in each level.

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/balc_guiraudr.png)

<a id='PELIC'></a>
### 2.2. PELIC

PELIC has [over 40,000 texts](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/PELIC_data.ipynb#trim), so I had to cut-down on what I wanted to examine. I picked only first-version texts from writing class that were in levels 3-5 from native speakers of Arabic, Spanish, and Korean, and still ended up with around [6,000 files](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/exploratory-analysis/PELIC_data.ipynb#describe).

The essays in PELIC are, on average, much longer than those in the CEPA texts, which can be seen below. Part of this is probably due to the format of the CEPA assessment, where students have 30 minutes to write an essay in English by hand.

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/pelic_tokencts.png)

<a id='3'></a>
### 3. Linguistic analysis

<a id='articles'></a>
### 3.1. Articles in PELIC
Surprisingly, although _the_ is the most common word in English, the most prevalent article in PELIC as tagged by my [function]() was the zero article, both corpus-wide and within each L1. Korean L1 speakers were more likely to use the indefinite article than either Arabic or Spanish L1 speakers, but this was a slight increase.

Articles in the corpus as a whole:
![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/pelic_allarticles_pie.png)

Spanish L1 speakers were most likely to use the definite article, typically followed by Arabic L1 speakers (except for in level 3).

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/pelic_alldefns_bylvl-L1.png)

Korean L1 speakers were most likely to use the indefinite articles, and Arabic L1 speakers the least likely.

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/pelic_allindefns_bylvl-L1.png)

In level 3, Korean speakers were most likely to use the zero article, followed by Spanish L1, with Arabic L1 speakers the least likely to use them. In Level 4, all groups increase their usage of the zero article, with Korean and Spanish L1 speakers seeming to be about the same usage and Arabic L1 slightly less than them. In Level 5, speakers in all three of these L1s seem to be using them about the same amount.

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/pelic_allzerons_bylvl-L1.png)

<a id='errors'></a>
### 3.2. Article errors in PELIC

To compute article errors automatically can be a bit tricky, so I decided to look at plural common nouns that were preceded by an indefinite article. There understandably weren't a lot, as seen below, but there were a few.

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/pelic_plns_indef.png)

I looked at the most common plural nouns following an indefinite article, and was actually a bit surprised that most of them were regular plurals with the morphological plural _-s_. In fact, across the entire corpus (L1 not taken into account), only two of these nouns were irregular plurals ('people' and 'men').

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/pelic_plnsindef_common_all.png)

As can be seen below, Arabic L1 speakers had the most errors of this type, followed by Korean L1 speakers. Spanish speakers actually only had ten total instances of this type of error, period.

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/pelic_plnsindef_common_ara.png)

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/pelic_plnsindef_common_kor.png)

![png](https://github.com/Data-Science-for-Linguists-2019/ESL-Article-Acquisition/blob/master/images/pelic_plnsindef_common_spa.png)

<a id='usage'></a>
### 3.3. Qualitative analysis of article usage

Three samples for each L1 at level 3 were used to do a small amount of qualitative analysis.

The Arabic L1 speakers seemed to have high accuracy with the use of the zero article, especially in front of plural nouns. Generic reference and reference to abstract non-count nouns were harder for learners, and in these contexts, learners tended to use the definite article instead of the zero article, producing errors such as:
1. Parents should help their children be aware of _the_ wrong and _the_ right in order that they will know why their parents want them to follow their advice.
2. _The_ money is the root of all evil.

Indefinite articles almost never appeared outside of the context of first mention (3) or non-specific indefinite reference (4).
3.	…I went to _a_ soup kitchen to serve food to people who can’t get food easily.
4.	For those who aren’t be educated how to be good teachers, it might be _a_ very big problem.

Spanish L1 learners in Level 3 seem to be more comfortable with indefinite articles than Arabic L1 learners, based on a higher appearance of the articles a and an. It most commonly used in non-specific indefinite reference and first mention contexts, which is expected. However, they did occasionally overgeneralize the usage of the, even in first-mention contexts such as:
6.	finally, every day i will eat my favorite food because in my apartament _the_ chef will cook.  

Korean L1 learners in Level 3 seem to avoid using the definite article and prefer to use the zero article and then indefinite articles. When _the_ is used, it is most often used with superlatives and post modified non-count nouns, as seen in examples (7a) and (7b). The definite article was occasionally overgeneralized (seen in example 8a), but more common was the overgeneralization of indefinite articles, even in contexts where a nominal object was missing (8b).
7.
- (a) _The_ most popular field is business and management.
- (b) I think it is because of _the_ history of our family.
8.
- (a) My room center has _the_ heart shape rug.
- (b) It is _a_ bigger than business and management or engineering.

<a id='4'></a>
## 4. Conclusion

<a id='learn'></a>
### 4.1. What I learned
As I said, I learned a lot about cleaning data, coding, and verifying the corpus structure instead of just trusting what you're told. I also learned about different measures of lexical complexity.

As seen from the corpus-wide quantitative analysis, the zero article was the most prevalent article in the corpus in all L1s. While this may at first seem strange, it follows points made by Palmer (1939) and Master (1997), which suggest that the most common form in the English language may not be the definite article _the_, but instead the zero article _Ø_. However, this a bit weird to think about, since that's an invisible form.

Additionally, I did see that Korean L1 learners were the most likely to use indefinite articles, and that Arabic L1 learners seemed to be avoiding them, especially compared to Spanish L1 learners.

<a id='forward'></a>
### 4.1. Moving forward
Future directions for this line of research would be, first and foremost, to analyze more data and run statistical tests on results to look for significance. It would also be worth looking into improving and further investigating the article makeup of the different corpora.
