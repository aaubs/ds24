---
title: "Basics of NLP"
weight: 1
disableToc: true
draft: true
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


# Analysis of Political Tweets during the 2020 Presidential Debate

## Context
We'll analyze political tweets from around the time of the US Presidential Debate in October 2020, with a primary focus on distinguishing tweets from Democrats and Republicans. Additionally, we will explore discussed topics and comprehend the factors driving the predictions.

![](https://ichef.bbci.co.uk/news/800/cpsprodpb/E505/production/_114692685_uspresidentialdebate2020timedonaldtrumpandjoebiden.jpg)


## Datasets
1. **Political tweets:** Preprocessed and labeled (1: Democrats, 0: Republicans).
   - `https://github.com/SDS-AAU/SDS-master/raw/master/M2/data/pol_tweets.gz`
   
2. **Debate tweets:** From around the time of the debate in October 2020 (8,000 entries).
   - `https://github.com/SDS-AAU/SDS-master/raw/master/M2/data/pres_debate_2020.gz`

Both datasets are in JSON format.

## Task Overview
1. **Primary Task:** Build a classifier that can distinguish between Dem/Rep tweets.
2. **Bonus:**
   - Explore the discussed topics.
   - Identify what influences predictions using LIME.

---

## Step-by-Step Instructions

### 1. Data Preparation and Preprocessing
#### a. Data Import
- Load the datasets using pandas' `read_json` method.

#### b. Text Preprocessing
- Utilize `tweet-preprocessor` for cleaning tweets (remove URLs, numbers, reserved words, mentions, and emojis).
- Use SpaCy for lemmatization, lowercasing, and removal of stop words, punctuation, and non-alphabetic characters.
   
#### c. Text Vectorization
- Implement `TfidfVectorizer` to convert the text data into numerical format suitable for ML.

#### d. Handle Imbalanced Data (if needed)
- Employ a method such as random under-sampling to handle class imbalances.

### 2. Model Building
#### a. Model Selection
- Choose a classification model (e.g., Logistic Regression, XGBoost).

#### b. Model Training
- Split the data into training and testing sets.
- Train the model using the training data.

#### c. Model Evaluation
- Evaluate the model using appropriate metrics like precision, recall, f1-score, and accuracy.
   
### 3. Model Explainability using LIME
- Implement `lime` to explain the predictions made by the model.
- Analyze and interpret the results, focusing on how different features (words) impact the predictions.

### 4. Topic Modelling
#### a. Text Tokenization
- Tokenize the processed text, focusing on nouns and adjectives.
   
#### b. Model Fitting
- Employ `LdaMulticore` for topic modeling and determine the topics discussed in the tweets.
- Optionally, you might also explore other models like LSI.

#### c. Visualization
- Use `pyLDAvis` to visualize the topics and understand their distribution and significance.

### 5. App Development using Gradio
#### a. UI Design
- Design a user interface with input for a tweet and output for the predicted label and explanation.

#### b. Integration
- Integrate the developed model and LIME explanations to return outputs for given tweet inputs. (optional)

#### c. Deployment
- Optionally, deploy the app for broader access.

### 6. Analysis and Conclusion
- Compile your findings, providing insights into distinguishing features, discussed topics, and model performance.
- Comment on the reliability and usability of your model and app.

---

## Notes and Tips
- **Data Privacy:** Ensure to comply with ethical and legal guidelines related to data usage and AI.
- **Exploration:** Consider visualizing word distributions and token frequencies.
- **Documentation:** Ensure to document each step and findings thoroughly in your Jupyter notebook.
- **Optimization:** Consider refining the model for better accuracy and reliability.

---

## Technologies & Libraries
- **Data Handling:** pandas, numpy
- **Text Preprocessing:** tweet-preprocessor, SpaCy
- **Modeling:** scikit-learn, xgboost, gensim
- **Explainability:** lime
- **Visualization:** altair, pyLDAvis
- **App Development:** gradio

**Important:** Ensure to install all the necessary packages using pip (e.g., `!pip install lime gradio`).

Good luck, and may your model classify accurately and provide enlightening explanations!

* [Notebook from class](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M2_politikal_tweet_workshop_class.ipynb)



<!--

### Context - Exercise: Presidential Debate 2020


Yes, we are going back in time to the Presidential Debate in the US 2020 - the time of lots of unhappy Tweeting. It's just too good a dataset and case to let it go...


### Data

* Political tweets: `https://github.com/SDS-AAU/SDS-master/raw/master/M2/data/pol_tweets.gz` from https://github.com/alexlitel/congresstweets We've preprocessed a bit to make things easier. 1: Dems. 0: Rep.

* Tweets around the time of the debate in oktober 20 (8000): `https://github.com/SDS-AAU/SDS-master/raw/master/M2/data/pres_debate_2020.gz`

Both datasets are in JSON format.
Task: Build a classifier that can distinguish Dem/Rep tweets. Bonus: 1. Explore discussed topics; 2. find out what drives predictions.


## Notebook

In-class-solution and add-ons (TM)

* [Political Tweets Prediction](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M2-pol_tweets_workshop.ipynb) -->