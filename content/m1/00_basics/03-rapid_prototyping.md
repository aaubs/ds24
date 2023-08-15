---
title: "Rapid Prototyping (W 37)"
weight: 3
disableToc: true
draft: false
---

![](/ds22/images/ds_corgi.png)
Corgi working on a Data Science project. 2022. Roman x [Stable Diffusion](https://stability.ai/blog/stable-diffusion-public-release)


The Rapid Prototyping with Streamlit & Gradio course will teach students how to use Streamlit and Gradio to create interactive web applications and dashboards. Students will learn the basics of rapid prototyping, and they will explore how Streamlit and Gradio can be used to turn data scripts into interactive web applications. They will also learn how to deploy their applications as web apps.

In the Real-World Data to Online Dashboard session, students will start with a real-world dataset and use it to create an interactive online dashboard. They will learn how to visualize geographic data effectively, and they will integrate the geographic visualizations into their dashboard. They will also learn how to host and deploy their dashboard online.

The Dashboard-Hackathon Kick-off session will give students the opportunity to compete in a hackathon to create the most compelling and user-friendly dashboard using Streamlit. TAs will be on hand to help kickstart ideas, troubleshoot, and refine dashboards. The final dashboards should be hosted and shared by September 15th, and great prizes await the top dashboards!

## Part1: Rapid Prototyping with Streamlit & Gradio
* Prototyping Foundations: Grasp why rapid prototyping is essential in Data Science and its role in iterative development and deployment.
* Streamlit Introduction: Dive into Streamlit, a Python library that makes it easy to turn data scripts into interactive web applications.
* Gradio Exploration: Learn about Gradio, an interface library for quickly creating demos and UIs for machine learning models.

Deployment: Deployment of projects as WebApps

## Part 1: AirBnb
In this notebook we will be using data from AirBnb for some basic EDA and geoplotting

* [EDA and Geoviz starter](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1-airbnb-eda-geoplot-starter.ipynb)
* [EDA and Geoviz class](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1-airbnb-eda-geoplot-class.ipynb)

## Part 2: Kaggle

In this notebook we will be learning how to work with data from Kaggle as well as exercise more simple data-viz.
* [Kaggle starter](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1-kaggle-class.ipynb)
* [Kaggle class](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1-kaggle-class.ipynb)


### What to do now?!
* Replay code from the course and see if you do understand the core mechanics - you DO NOT need to remember everything.
* [Android app market project on datacamp](https://app.datacamp.com/learn/projects/android-app-market)
* [Course: Python DS toolbox 1](https://app.datacamp.com/learn/courses/python-data-science-toolbox-part-1) & [Course: Python DS toolbox 2](https://app.datacamp.com/learn/courses/python-data-science-toolbox-part-2)
* [Opendata.dk](https://admin.opendata.dk) - build a map of different attractions in Aalborg based on public data. See preprocessing example - how to get data out of nested JSON - below:

**This is how you can preprocess the GeoCoordinates from the JSON file:**

```python
#Load pandas
import pandas as pd

# Read the file from remote
data = pd.read_json('https://admin.opendata.dk/dataset/44ecd686-5cb5-40f2-8e3f-b5e3607a55ef/resource/eeabb0f8-1b19-4c80-b059-5ba5c4c872d2/download/guidedenmarkaalborgenjson.json')

# The GeoCoordinates are hiding in the Address column
data['Address'][0]['GeoCoordinate']

# You can use list comprehension to pull out GeoCoordinates (also empty values) - try out
# This will allow you to filter for missing data without fancy workarounds
[x['GeoCoordinate'] for x in data['Address']]

# Make a new column based on that to be used for filtering out missing data
data['GeoCoordinate'] = [x['GeoCoordinate'] for x in data['Address']]

# drop, where no GeoCoordinate
data = data.dropna(subset=['GeoCoordinate'])

# Pull out the values
data['latitude'] = [x['Latitude'] for x in data['GeoCoordinate']]
data['longitude'] = [x['Longitude'] for x in data['GeoCoordinate']]
````

### Introduction to GeoPandas

Using GeoPandas to analyze geospatial data will be our focus in this notebook.

* [GeoPandas](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1-GeoPandas-Part1.ipynb)
* [GeoPandas exercises](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1-GeoPandas-Exercises.ipynb)