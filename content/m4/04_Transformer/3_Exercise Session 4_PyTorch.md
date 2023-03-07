---
title: "Exercise Session 4"
weight: 3
disableToc: true
draft: false
---

In this session, you will learn how to upload your fine-tuned HuggingFace model and deploy it using two different platforms: Streamlit and Gradio. First, you will learn how to properly upload your model to the HuggingFace Hub, a platform that allows you to easily share and access models. Then, you will learn how to use Streamlit and Gradio, two user-friendly platforms, to deploy your model and make it accessible to others. By the end of this session, you will be able to confidently upload and deploy your models for use by others.

### How to upload your fine-tuned model on HuggingFace
First, it logs in to the Hugging Face Hub using notebook_login(), which allows for easy uploading and access to Hugging Face models.
```python
#Importing the necessary libraries
from huggingface_hub import notebook_login
from transformers import pipeline

#Login to Hugging Face account from the Jupyter notebook
notebook_login()
````
Next, it pushes the trainer object, model object, and dataset object to the Hub using their push_to_hub() methods. This uploads these objects to the Hub for others to use and access.

```python
#Pushing the trained model, trainer and dataset to the Hugging Face Hub
trainer.push_to_hub(output_dir)
model.push_to_hub(output_dir)
dataset.push_to_hub('Your Fine-Tuned HuggingFace Model')
````
Finally, the code loads a pre-trained Danish emotion classification model using model_ckpt = 'Your Fine-Tuned HuggingFace Model', and creates a pipeline using the pipeline() method from the transformers library. This pipeline can then be used to classify text inputs into one of several emotional categories.

```python
#Defining the path to the trained model checkpoint on the Hugging Face Hub
model_ckpt = 'Your Fine-Tuned HuggingFace Model'

#Creating a pipeline for example text classification using the fine-tuned model from the Hugging Face Hub
pipe = pipeline('text-classification', model=model_ckpt)

#Passing the Danish text examples to the pipeline and getting the predicted labels
pipe(['Du er en idiot!', 'Jeg er sulten!'])
````

### How to deploy your fine-tuned model on HuggingFace
You can also deploy your fine-tuned Hugging Face model on Streamlit through the Hugging Face web interface. Here are the steps to do so:

1. After uploading your fine-tuned Hugging Face model to the Hugging Face Model Hub, create a new space in your Hugging Face profile and enter the details for your app, including the name of your application.
2. Select "Streamlit" (or Gradio) as the deployment type.
3. click "New space".
4. Upload your app.py and requirements.txt files to the Hugging Face web interface.
5. Your app is automatically deployed.

That's it! Your fine-tuned Hugging Face model is now deployed on Streamlit through the Hugging Face web interface and can be accessed using your app.

#### Two Simple Examples for Deploying an App using Streamlit and Gradio
**Danish text sentiment analysis using Gradio:**

```python
# app.py
import gradio as gr
from transformers import pipeline
from transformers import AutoTokenizer, AutoModelForSequenceClassification

#Defining the classify function which takes text as input and returns the label of the sentiment
def classify(text):
  # Initializing the pipeline for sentiment analysis
  cls = pipeline('text-classification', model='RJuro/dk_emotion_bert_in_class')
  # Predicting the sentiment label for the input text
  return cls(text)[0]['label']

#Creating the Gradio interface with input textbox and output text
gr.Interface(fn=classify, inputs=["textbox"], outputs="text").launch()
````

```python
# requirements.txt
transformers
gradio
torch
''''