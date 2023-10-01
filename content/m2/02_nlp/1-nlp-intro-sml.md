---
title: "Basics of NLP"
weight: 1
disableToc: true
draft: false
---

![](/ds23/images/M2_nlp_dog1.jpg)
Medieval clergy, smartphones and dogs 2023. Roman x Stable Diffusion XL


This session introduces basic concepts of NLP. 
We will take a Problem-Based-Learning approach and I will introduce NLP-related concepts as we go. If you need a more theoretical intro (standalone), I'll uploaded pre-recorded videos. We will start with a project based on

## Context

This assignment is based on data from [this paper](https://ojs.aaai.org/index.php/ICWSM/article/download/14955/14805)
> Davidson, T., Warmsley, D., Macy, M., & Weber, I. (2017, May). Automated hate speech detection and the problem of offensive language. In Proceedings of the international AAAI conference on web and social media (Vol. 11, No. 1, pp. 512-515).

You are given a collection of approximately 25k tweets that have been manually (human) annotated.  ```class``` denotes: 0 - hate speech, 1 - offensive language, 2 - neither

```https://github.com/SDS-AAU/SDS-master/raw/master/M2/data/twitter_hate.zip```

![hatespeech](https://static.dw.com/image/56177307_303.jpg)

## 1. Preprocessing and vectorizaion. 
Justify your choices and explain possible alternatives (e.g. removing stopwords, identifying bi/tri-grams, removing verbs or use of stemming, lemmatization etc.)

- Create a bag-of-words representation, apply TF-IDF and dimensionality reduction (LSA-topic modelling alternatively simply PCA or SVD) to transform your corpus into a feature matrix.

## 2. Explore and compare the 2 "classes of interest" - hate speech vs offensive language. 

- Can you see differences by using simple count-based approaches?
- Can you identify themes (aka clusters / topics) that are specific for one class or another? Explore them using, e.g. simple crosstabs - topic vs. class and to get more detailed insights within-cluster top (TF-IDF) terms. (This step requires preprocessed/tokenized inputs).

## 3. Build an ML model that can predict hate speech
Use the ML pipeline (learned in M1) to build a classification model that can identify offensive language and hate speech. It is not an easy task to get good results. Experiment with different models on the two types of text-representations that you create in 2.

Bonus: Explore missclassified hate speech tweets vs those correctly predicted. Can you find specific patterns? Can you observe some topics that are more prevalent in those that the model identifies correcly?

The best-reported results for this dataset are.

| Class         | Precision     |
| ------------- |:-------------:|
| 0             |0.61           |
| 1             |0.91           |
| 2             |0.95           |
| Overall       |0.91           |


## Notebook

This notebook contains an extended solution.

* [Hate Speech Detection](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M2_hatespeech_nlp_explainer_tm_2023.ipynb)

<!--

### Context - Exercise: Presidential Debate 2020


Yes, we are going back in time to the Presidential Debate in the US 2020 - the time of lots of unhappy Tweeting. It's just too good a dataset and case to let it go...

![](https://ichef.bbci.co.uk/news/800/cpsprodpb/E505/production/_114692685_uspresidentialdebate2020timedonaldtrumpandjoebiden.jpg)

### Data

* Political tweets: `https://github.com/SDS-AAU/SDS-master/raw/master/M2/data/pol_tweets.gz` from https://github.com/alexlitel/congresstweets We've preprocessed a bit to make things easier. 1: Dems. 0: Rep.

* Tweets around the time of the debate in oktober 20 (8000): `https://github.com/SDS-AAU/SDS-master/raw/master/M2/data/pres_debate_2020.gz`

Both datasets are in JSON format.
Task: Build a classifier that can distinguish Dem/Rep tweets. Bonus: 1. Explore discussed topics; 2. find out what drives predictions.


## Notebook

In-class-solution and add-ons (TM)

* [Political Tweets Prediction](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M2-pol_tweets_workshop.ipynb) -->