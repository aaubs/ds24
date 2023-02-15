---
title: "Exercise Session 3"
weight: 3
disableToc: true
draft: false
---

In this session, you will learn how to finetune SBERT embeddings and use them in downstream tasks. They will also practice using SBERT in a variety of business scenarios.


## Hate Speech Dataset

![](https://media.licdn.com/dms/image/C4D12AQGixW0ur9HJgg/article-cover_image-shrink_423_752/0/1520125944764?e=1681948800&v=beta&t=HGNUzbylZaCSKZBQy-ajyeUfL9oUAZv5plMLChAhfck)

> Online hate speech on social media networks can influence hate violence and even crimes against a certain group of people in this digital age. According to FBI statistics, hate-related attacks on specific groups of people are at a 16-year high ![1](https://www.nytimes.com/2019/11/12/us/hate-crimes-fbi-report.html). Due to this, there is a growing need to eradicate hate speech through automatic detection to reduce the burden on moderators Datasets were obtained from Reddit and a white supremacist forum, Gab, where human-labeled comments are classified as hate speech ![2](https://github.com/jing-qian/A-Benchmark-Dataset-for-Learning-to-Intervene-in-Online-Hate-Speech). 


### Overview

The dataset used for this project consists of Tweets labeled as hate_speech, offensive_language, or neither. In the dataset:

* count = number of CrowdFlower users who coded each tweet (min is 3, sometimes more users coded a tweet when judgments were determined to be unreliable by CF).
* hate_speech = number of CF users who judged the tweet to be hate speech.
* offensive_language = number of CF users who judged the tweet to be offensive.
* neither = number of CF users who judged the tweet to be neither offensive nor non-offensive.
* class = class label for majority of CF users.
* 0 - hate speech 1 - offensive language 2 - neither



### Tasks

* First step: The performance of Transformer models and traditional models for computing embeddings
* Second step: SBERT for semantic similarity (Patent Search using PatentSBERTa)


## Notebooks

Here you will find the notebooks for this session:

* [TF-IDF and W2V Multi-Class Text Classification](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M4_TFIDF_W2V_multiclass_text_classification.ipynb)
* [Implementing RNNs using PyTorch - Exercise](https://github.com/aaubs/ds-master/blob/main/notebooks/M3_RNN_Exercise_Seession_2.ipynb)
* [Implementing LSTMs using PyTorch](https://github.com/aaubs/ds-master/blob/main/notebooks/M3_LSTM_Tutorial.ipynb)
* [Implementing LSTMs using PyTorch - Exercise](https://github.com/aaubs/ds-master/blob/main/notebooks/M3_LSTM_Exercise_Seession_2.ipynb)
* [Implementing LSTMs using PyTorch - Solution](https://github.com/aaubs/ds-master/blob/main/notebooks/M3_LSTM_Exercise_Seession_2_Solution.ipynb)
* [Implementing LSTMs using PyTorch - Text Generation](https://github.com/aaubs/ds-master/blob/main/notebooks/M3_Character_Level_LSTM_PyTorch.ipynb)
* [Implementing LSTMs using PyTorch - Text Generation with embeddings layer]()

## Resources

* [PyTorch](https://pytorch.org/docs/stable/nn.html)
* [PyTorch NN Linear](https://www.sharetechnote.com/html/Python_PyTorch_nn_Linear_01.html)

