---
title: "Intro to GPT Models"
weight: 5
disableToc: true
draft: false
---

![](http://jalammar.github.io/images/gpt2/gpt2-sizes-hyperparameters-3.png)

GPT models (Decoders) play a crucial role in generating subsequent words in tasks like text translation or story generation, providing outputs along with their probabilities. They utilize attention mechanisms twice during training: initially, Masked Multi-Head Attention, where only the beginning of a target sentence is revealed, and later, Multi-Head Attention, similar to encoders. In traditional transformer models, decoders interact with encoders by using the encoder's outputs to assist in tasks like sentence translation. However, GPT models adopt a unique approach by relying solely on a decoder, compensating for the absence of an encoder through extensive training on large datasets. This allows for embedding a vast amount of knowledge within the decoder. ChatGPT further advances these techniques by integrating human-labeled data to address issues such as hate speech and employing Reinforcement Learning for enhanced model quality.

## Notebooks - Basics

* [Generative Pre-trained Models - Basics](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_NLG_4.ipynb)
* [Generative Pre-trained Models - Basics - Solutions](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_NLG_4_Solutions.ipynb)

## Notebooks - Applications

* [TM Applications - LangChain](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_Into_LangChain_v1.ipynb)
* [TM Applications - LanceDB](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_LanceDB_v2.ipynb)
* [TM Applications - LanceDB - Solutions](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_LanceDB_v2_Solutions.ipynb)
* [TM Applications - RAG](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_NLG_3_RAG_Mistral_v2.ipynb)

## Notebooks - FineTuning

* [Prompt Engineering](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_NLG_prompt_engineering_v2.ipynb)
* [PEFT - LoRA](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_Finetune_opt_bnb_peft.ipynb)


## Resources

- [LangChain](https://python.langchain.com/docs/get_started/quickstart)
- [LanceDB - Vector database](https://lancedb.github.io/lancedb/)
