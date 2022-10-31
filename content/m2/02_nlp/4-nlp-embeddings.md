---
title: "NLP Word Embeddings"
weight: 4
disableToc: true
draft: false
---

![](/ds22/images/viz-corgi-nlp-w2v.png)
Roman x [Stable Diffusion](https://stability.ai/blog/stable-diffusion-public-release)

Word embeddings such as Word2Vec or fastText are probably the last techology in NLP before the deep learning revolution. Others would argue that they paved the way for DL becoming the NLP standard.
May that as it be, it's a powerfull approach and in this tutorial you will learn about the theory behind these word representations, how they are trained (also from disk).
We will also explore approaches to representing text using pretrained vectors.

By the way: Embeddings can also be used non-sequential inputs. Here a cool project where recipes are used to create food-vectors: [Food2Vec](https://jaan.io/food2vec-augmented-cooking-machine-intelligence/
)
<div style="position: relative; padding-bottom: 0; height: 0;"><iframe src="https://jaan.io/files/food2vec_food_embeddings_tsne.html" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

We are actually also going to work with food related data...

## Notebook

[{{< awesome fas fa-laptop-code >}} Training Chatbot](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M2-training-word-vectors.ipynb)