---
title: "Fine-tuning transformers"
weight: 1
disableToc: true
draft: false
---


![](/ds22/images/corgi_workshop.png)

## Resources
* You will need a HF🤗 account to upload models
* We will use [WandB for monitoring](https://wandb.ai/home) - get an account if you like to follow that part
   
## Notebooks

* [Transformer-based Translation (inference)](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_HyggeBERT_translation_en_da.ipynb)

* [Finetuning Sequence Classification with Bert](https://colab.research.google.com/drive/1LFBgde5VEhktGw_LYnvNhKFKCB7HJzfs?usp=sharing)


## Homework - As a preparation for final assignment‼️

### Finetune a model for token-classification
- Follow [this tutorial](https://huggingface.co/course/chapter7/2?fw=pt)
- Cheating option 1: [NERDA](https://ebanalyse.github.io/NERDA/), Thanks to the lovely people at Ekstrabladet/PIN
- Cheating option 2: [Simpletransformers](http://simpletransformers.ai)
- Try custom Named Entities [Skills](https://github.com/kris927b/SkillSpan), [Scientific Terms](http://nlp.cs.washington.edu/sciIE/)
- Make your own NER dataset using [Argilla and 0-shot labeling with Flair](https://docs.argilla.io/en/latest/tutorials/notebooks/labelling-tokenclassification-flair-fewshot.html) - you can deploy argilla with 1-click on 🤗 spaces and connect to it via e.g. Colab.

### Nerd-out options
- GPT-2 finetuning. Make it produce text in a certain style. Follow [this tutorial](https://github.com/philschmid/fine-tune-GPT-2/blob/master/Fine_tune_a_non_English_GPT_2_Model_with_Huggingface.ipynb)
- Build a retreival based Question-Answering system with [🦜⛓️LangChain][https://langchain.readthedocs.io/en/latest/]