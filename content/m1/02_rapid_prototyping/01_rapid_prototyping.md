---
title: "Introduction to Streamlit: Building an Employee Attrition Dashboard"
weight: 1
disableToc: true
draft: false
---


![](/ds22/images/ds_corgi.png)
Corgi working on a Data Science project. 2022. Roman x [Stable Diffusion](https://stability.ai/blog/stable-diffusion-public-release)

# Introduction to Streamlit

Streamlit is a fast and easy way to create web apps for data analysis and visualization using Python. In this tutorial, we will be building an **Employee Attrition Dashboard** to showcase the power and ease of Streamlit.

## What You'll Build

By the end of this tutorial, you'll have a functional dashboard that allows users to:
- Filter data based on various employee metrics.
- Visualize attrition rates and patterns across different dimensions.
- Understand insights from visualizations.
- Get actionable recommendations based on data insights.

## Prerequisites

Before you begin, ensure you have the following:
- Basic knowledge of Python.
- Streamlit installed (`pip install streamlit`).
- Familiarity with data visualization libraries like `altair`, `matplotlib`, and `seaborn`.

## Getting Started

### 1. Data Source

We'll use a synthetic dataset on employee attrition from this [link](https://raw.githubusercontent.com/aaubs/ds-master/main/apps/M1-attrition-streamlit/HR-Employee-Attrition-synth.csv).

### 2. File Structure

Ensure your working directory has the following structure:

📦Your_Directory
 ┣ 📜app.py
 ┗ 📜requirements.txt
 ┗ 📜data.csv


`app.py` will contain our Streamlit app's code, while `requirements.txt` will list the necessary Python packages.

### 3. Hosting the App

Once you've built the app, we'll first host it on **Streamlit Cloud** and then on **uCloud** (A Danish private cloud for universities).

## Building the Dashboard

[Here's the code to build the dashboard](https://github.com/aaubs/ds-master/blob/main/apps/M1-attrition-streamlit/app.py). Go through it, and let's break it down.


### Initialization

We start by importing necessary libraries and loading our dataset. The data is cached using `@st.cache_data` to enhance performance.

### Designing the Interface

Streamlit provides intuitive functions to design the user interface:
- `st.title()` and `st.header()` set titles and headers.
- `st.markdown()` allows for rich text formatting.
- `st.sidebar` lets you add interactive widgets in a sidebar for filtering.

### Visualizations

Depending on user input, we visualize the filtered data using various charts. For instance, `altair` is used for bar and pie charts, while `matplotlib` and `seaborn` provide KDE plots and boxplots.

### Insights and Recommendations

Finally, expanders provide a space to share insights derived from visualizations and actionable recommendations.

## Conclusion

Streamlit offers a user-friendly platform to build and deploy interactive data apps without the need for extensive web development skills. Dive in, explore the code, and customize it to create your own data-driven web applications.

---

**Happy Coding!** 🚀
