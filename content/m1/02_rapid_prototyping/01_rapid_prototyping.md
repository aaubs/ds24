---
title: "Introduction to Streamlit: Building an Employee Attrition Dashboard"
weight: 1
disableToc: true
draft: false
---

![](/ds23/images/ds_corgy_23_c.jpg)
Corgi working on a Data Science project. 2023. Roman x [Stable Diffusion XL](https://stability.ai)


Streamlit has rapidly become a go-to tool for data scientists and developers wanting to turn data scripts into shareable web apps. Let's explore its core features and benefits:

## Key Features of Streamlit

1. **Simplicity**: With just a few lines of Python code, you can have a running web application. No need to deal with HTML, CSS, or JavaScript unless you want to.
2. **Interactive Widgets**: Streamlit offers out-of-the-box widgets like sliders, buttons, and text inputs that make your app interactive.
3. **Data Integration**: It seamlessly integrates with popular data science libraries like Pandas, Numpy, Matplotlib, and others.
4. **Data Caching**: With `@st.cache`, Streamlit caches the output of functions, ensuring your data operations are efficient and your apps remain performant.
5. **Hot Reloading**: As you save changes to your script, the app refreshes in real-time. No need to manually restart your app.

## vs. [Gradio](https://www.gradio.app/) 

While Streamlit offers a robust platform for creating web apps, Gradio provides several distinct advantages, especially when the focus is on deploying machine learning models:

1. **Ease of Model Deployment**: Gradio prioritizes simplifying the deployment of machine learning models. Its intuitive Python API allows for quick interface generation, ensuring accessibility even for non-experts.
2. **Diverse Input Types**: Gradio supports a wide variety of input formats, from images and text to audio, providing flexibility especially when dealing with different data types.
3. **Multi-Model Deployment**: Gradio stands out with its capability to simultaneously deploy multiple models, perfect for ensemble methods or side-by-side model comparisons.
4. **Shareability**: Gradio's feature of generating shareable URLs makes collaboration and showcasing a breeze.
5. **Security Features**: Gradio offers built-in adversarial robustness, adding an extra layer of protection against potential adversarial attacks on deployed models.

These unique features make Gradio an attractive option for projects that focus on deploying and sharing machine learning models with diverse requirements. We are going to explore gradio after introductions to ML.


## Why Choose Streamlit?

- **Rapid Prototyping**: Streamlit's intuitive API and hot reloading mean you can quickly iterate and refine your app.
- **Open Source**: Being open-source, it boasts a strong community that contributes to its growth and offers a plethora of community plugins.
- **Deployment Ready**: With platforms like Streamlit Sharing, deploying your app to the world is just a click away.
- **Extensible**: You can integrate advanced JavaScript features or even other Python libraries to extend Streamlit's capabilities.

## Core Components of Streamlit

### Layout and Widgets

- **Layout**: `st.columns` and `st.container` can be used to design your app's layout.
- **Widgets**: These are interactive elements like `st.slider()`, `st.selectbox()`, and `st.button()` that capture user input.

### Display Elements

- **Media**: Display images, videos, or audio clips using `st.image()`, `st.video()`, and `st.audio()`.
- **Charts**: Use `st.line_chart()`, `st.bar_chart()`, or integrate with libraries like Altair for custom visualizations.
- **Tables**: Showcase data with `st.table()` or `st.dataframe()`.

### Session State

- **State**: Store user data or app state across reruns with `st.session_state`.

## Dive Deeper

To truly master Streamlit, it's recommended to experiment with building various apps and exploring its [official documentation](https://docs.streamlit.io/). The community is active, and there's always something new to learn!


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

```bash
📦Your_Directory
 ┣ 📜app.py
 ┗ 📜requirements.txt
 ┗ 📜data.csv
 ```


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

## Access the Deployed App

You can access the final deployed Employee Attrition Dashboard on Streamlit using the link below:

[Employee Attrition Dashboard](https://m1-attrition-app-5axd6zprgn57jmwujpjuhn.streamlit.app)

Feel free to explore the app, interact with the various filters and visualizations, and gain insights into employee attrition patterns.


## Conclusion

Streamlit offers a user-friendly platform to build and deploy interactive data apps without the need for extensive web development skills. Dive in, explore the code, and customize it to create your own data-driven web applications.



**Happy Coding!** 🚀


## Old corgy from last year...
![](/ds22/images/ds_corgi.png)
Corgi working on a Data Science project. 2022. Roman x [Stable Diffusion](https://stability.ai/blog/stable-diffusion-public-release)