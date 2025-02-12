---
title: "Group Assignment 2: Transformer Models for Classification"
weight: 4
disableToc: true
draft: False
---

<!-- # Portfolio Exercise 2: Transformer Models for Classification -->
> **Note:** M3 - Group Assignment 2 Deadline: Monday 17th of Feb


![Corgi Pups Neon Image](/ds22/images/corgi_pups_neon.png)

## Introduction

This exercise is designed to deepen your understanding and skills in modern deep learning techniques with a focus on classification tasks. In this assignment, you are required to fine-tune a transformer model for one of the following classification tasks:

- **Binary Classification**
- **Multi-Class Classification**
- **Multi-Label Classification**

You can choose any dataset (from 🤗 Hugging Face Datasets, Kaggle, or your own collection) that is suitable for the classification task you wish to address.

## Task Description

Your assignment involves the following key steps:

1. **Dataset Selection and Preprocessing**
   - Choose a dataset appropriate for your chosen classification task (binary, multi-class, or multi-label).
   - Preprocess the data as needed (e.g., tokenization, handling class imbalance, etc.).

2. **Model Selection and Fine-Tuning**
   - Use a transformer model (e.g., BERT, RoBERTa, DistilBERT, etc.) available from Hugging Face.
   - Fine-tune the model on your selected dataset using libraries such as Simple Transformers or Hugging Face Transformers.
   - Document your training process, including hyperparameter choices, evaluation metrics, and any challenges encountered.

3. **Evaluation**
   - Evaluate your fine-tuned model using appropriate metrics (e.g., accuracy, F1-score, ROC-AUC for binary; precision, recall, etc.).
   - Provide a brief analysis of the model’s performance on the test set.

4. **Deployment (Optional)**
   - Optionally, develop a simple web application using Streamlit or Gradio that allows users to input text and see classification predictions.
   - This step is meant to demonstrate how your model can be deployed in a real-world scenario.

5. **Upload to Hugging Face Hub**
   - Once fine-tuning is complete, upload your model to the [Hugging Face Hub](https://huggingface.co/) and provide a link to the repository.
   - Ensure that your model card includes information about the dataset, training parameters, evaluation metrics, and intended use.

## Data

- You may utilize datasets from 🤗 Hugging Face, Kaggle, or create your own.
- Ensure that you cite your data source appropriately in your documentation.

## Delivery

1. **GitHub Repository**
   - Create a repository containing your code, notebooks, and documentation.
   - Include a **README.md** with a brief description of your assignment, your approach, and instructions on how to run your code.

2. **Colab or Jupyter Notebook**
   - Save your working notebook in the repository.
   - Ensure that the notebook includes detailed explanations of each step, from data preprocessing to model evaluation.

3. **Group Work**
   - You may work in groups of up to 3 members.
   - Each group member’s contribution should be briefly outlined in the README or the notebook.

4. **Technical Explainer Video**
   - Record a short (~5 minutes) **technical explainer video** presenting your main ideas, methodology, and results.
   - You may use Panopto, OBS Studio, Loom, or any other screen-recording tool.
   - Include the video link in your submission.

5. **Submission**
   - Send an email to Hamid (hamidb@business.aau.dk) with the link to your GitHub repository (and video) by the deadline.

---

**Good luck and have fun exploring classification with transformer models in PyTorch and Hugging Face!**
