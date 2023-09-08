---
title: "- Real World Data to Online Dashboard"
weight: 2
disableToc: true
draft: false
---

This session will focus on creating interactive online dashboards using real-world data. Students will learn how to select and clean data, create visualizations, and deploy their dashboards to the web.

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

Using GeoPandas to analyze geospatial data will be our focus in these notebooks.

* [GeoPandas](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1_GeoPandas_Part1_V3.ipynb)
* [GeoPandas Hands-on Project](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1_GeoPandas_Hands_on_Project_Part2.ipynb)

### GeoPandas Exercises

* [GeoPandas exercises](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1-GeoPandas-Exercises.ipynb)
* [GeoPandas exercises and solutions](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1_GeoPandas_Exercises_Solutions.ipynb)