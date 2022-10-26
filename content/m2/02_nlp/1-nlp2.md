---
title: "NLP - Other areas"
weight: 2
disableToc: true
draft: false
---

![](/ds22/images/viz-corgi-nlp2.png)
Corgies doing NLP - Medieval Fresco. 2022. Roman x [Stable Diffusion](https://stability.ai/blog/stable-diffusion-public-release)

This session will continue with statistical NLP techniques in a "less guided fashion".

## Plan for the day

- Finish up political tweets (dem/rep classifier)
- Vectorization, distance and similarity for text (maybe even Word2Vec)
- What research is published at AAUBS? (Scopus + Topic Models) - Hamid takes over.

### Homework
- Finish up reseach topic modeling
- Turning it into an app... (build & deploy a text classifier app - template code below)
- Can you beat the score? 🎃🎃🎃 [Spooky NLP](https://www.kaggle.com/competitions/spooky-author-identification)


```python
import streamlit as st
import pandas as pd
import numpy as np
import pickle
import preprocessor as prepro

import spacy
nlp = spacy.load('en_core_web_sm')

from sklearn.pipeline import make_pipeline
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.linear_model import LogisticRegression

import eli5

st.set_page_config(
    page_title="Hate-Finder 🔍",
    page_icon="🔍")

# write everything into one function that can be re-used later
def text_prepro(texts):
  """
  takes in a pandas series (1 column of a DF)
  removes twitter stuff
  lowercases, normalizes text
  """
  texts_clean = texts.map(lambda t: prepro.clean(t))
  texts_clean = texts_clean.str.replace('#','')

  clean_container = []

  for text in nlp.pipe(texts_clean, disable=["tagger", "parser", "ner"]):

    txt = [token.lemma_.lower() for token in text 
          if token.is_alpha 
          and not token.is_stop 
          and not token.is_punct]

    clean_container.append(" ".join(txt))

  return clean_container

@st.experimental_singleton
def load_model():
    pipe = pickle.load(open('hate_pipe.pkl','rb'))
    return pipe

pipe = load_model()

txt = st.text_area('Text to analyze', '''
Write here some (potentially hate-speech) text
    ''')

if st.button('Predict if HATE 😵'):
    to_analyse = text_prepro(pd.Series([txt]))
    result = pipe.predict(to_analyse)[0]
    st.write(['HATE!','Not nice!','All good!'][result])
```