---
title: "Portfolio Assignment 1"
weight: 2
disableToc: true
draft: false
---

> **Note:** M3 - Group Assignment 1 Deadline: *Monday, 10th Feb at 12:00*

## Introduction

In this assignment, you will deepen your understanding of **feature engineering**, **data preprocessing**, and **neural network modeling** in **PyTorch**. While we suggest using a **house pricing dataset** for illustrative purposes, you are **free to choose any dataset** of interest. Your goal is to build a neural network that can handle either:

1. **Cross-sectional data** (i.e., data without a time component; a single "snapshot" of many observations). In this case, you will use an **MLP (Multi-Layer Perceptron)**.
2. **Time-series data** (i.e., data with a temporal or sequential component). In this case, you will use an **RNN (Recurrent Neural Network)** variant (e.g., simple RNN, LSTM) to capture the temporal relationships.

Your primary objectives are:

1. Preprocess and engineer features from your chosen dataset.  
2. Build, train, and evaluate at least **one** neural network architecture in PyTorch:
   - **MLP** if you have cross-sectional data.  
   - **RNN** if you have time-series/sequential data.  
3. Experiment with hyperparameters (e.g., number of layers/neurons, activation functions, learning rates, epochs, etc.).  
4. Evaluate and discuss your results, using appropriate performance metrics.

---

## Task

1. **Feature Selection**  
   - Identify the most relevant features (columns) for predicting your target variable.  
   - Provide a rationale for why these features are important or hypothesized to be predictive.

2. **Feature Engineering**  
   - Create or transform features that might enhance predictive power.  
   - If you have time-series data, consider creating lag features or rolling statistics for the RNN.

3. **Data Preprocessing**  
   - Handle missing values (e.g., imputation, removal).  
   - Encode categorical features (e.g., one-hot encoding).  
   - Normalize/standardize numerical features (e.g., Min-Max or StandardScaler).

4. **Train-Test (or Train-Validation-Test) Split**  
   - Split your data into appropriate sets.  
   - Consider using a validation set or cross-validation to fine-tune hyperparameters.

5. **Define Your Neural Network Architecture in PyTorch**  
   - **MLP** (if your data is purely cross-sectional):  
     - At least 2 hidden layers.  
     - Common activation functions (e.g., ReLU, Sigmoid, Tanh).  
     - Consider using dropout or batch normalization if helpful.

   - **RNN** (if your data has a temporal/sequential dimension):  
     - At least 2 hidden layers.  
     - Use RNN, LSTM cells.  
     - Experiment with different numbers of hidden units and sequence lengths.

6. **Training Loop**  
   - Implement a standard PyTorch training loop.  
   - Specify an appropriate loss function (e.g., MSE for regression, CrossEntropy for classification).  
   - Choose an optimizer (e.g., Adam, SGD).  
   - Track metrics (training/validation loss, accuracy, or other relevant metrics).

7. **Hyperparameter Experiments**  
   - Test different hyperparameters (e.g., hidden layers, learning rate, batch size) to observe changes in performance.  
   - Record and discuss these experiments.

8. **Model Evaluation**  
   - Evaluate your final model(s) on the **test set**.  
   - Use appropriate metrics (e.g., RMSE, MAE, R² for regression tasks; accuracy, F1-score, etc. for classification tasks).  
   - Provide plots of the training process (loss curves, etc.) and any model diagnostics.

9. **Documentation & Discussion**  
   - Summarize which model and hyperparameter settings worked best.  
   - Discuss possible reasons for better or worse performance.  
   - Mention limitations or potential improvements.

---

## Data

- **Dataset**:  
  - You may use a **house pricing dataset** or **any other** dataset of your choosing. Examples:  
    - Kaggle’s [House Prices](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques) for cross-sectional data.  
    - A stock prices or energy consumption dataset for time-series.  

  - Make sure you have enough data to train and test your model adequately.

- **Possible Features**:  
  - **Cross-sectional**: purely numeric or categorical features.  
  - **Time-series**: sequential numeric data with timestamps.

---

## Delivery

1. **GitHub Repository**  
   - Create a repository containing your work.  
   - Include a **README.md** with a brief description of your assignment and how to run the code/notebook.

2. **Colab Notebook**  
   - Save your notebook in the repository.  

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

**Good luck and have fun exploring neural networks in PyTorch—whether you choose to predict house prices or tackle another dataset!**
