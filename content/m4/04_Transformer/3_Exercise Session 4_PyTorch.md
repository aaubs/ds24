---
title: "Exercise Session 4"
weight: 3
disableToc: true
draft: false
---

In this session, you will learn how to upload your fine-tuned HuggingFace model and deploy it using two different platforms: Streamlit and Gradio. First, you will learn how to properly upload your model to the HuggingFace Hub, a platform that allows you to easily share and access models. Then, you will learn how to use Streamlit and Gradio, two user-friendly platforms, to deploy your model and make it accessible to others. By the end of this session, you will be able to confidently upload and deploy your models for use by others.

## How to upload your fine-tuned model on HuggingFace
First, it logs in to the Hugging Face Hub using notebook_login(), which allows for easy uploading and access to Hugging Face models.

```python
#Importing the necessary libraries
from huggingface_hub import notebook_login
from transformers import pipeline

#Login to Hugging Face account from the Jupyter notebook
notebook_login()
````

