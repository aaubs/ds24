---
title: Lecture 1  Introduction to Serverless ML and Databases
weight: 1
disableToc: true
draft: true
---

![](/ds22/images/corgi_utopia.png)


Use GitHub repo https://github.com/saoter/SDS24_MLOps_L1, which contains lecutre slides, python scripts and dataset for the first lecture. 

## SLIDES
- [Lecture 1](https://github.com/aaubs/ds23/edit/master/content/m6/L1/MLOps_Lecture_1_slides.pdf)

## API
- [api_jokes.py](https://github.com/aaubs/ds23/edit/master/content/m6/L1/api_jokes.py) is an example of simple public API
- [api_finance.py](https://github.com/aaubs/ds23/edit/master/content/m6/L1/api_finance.py), [api_news.py](https://github.com/aaubs/ds23/edit/master/content/m6/L1/api_news.py) are examples of private API using API_key (You need to register to get your private key)
- [api_datasets.py](https://github.com/aaubs/ds23/edit/master/content/m6/L1/api_datasets.py) is an example of API Wrapper
- EXTRA: [joke_app.py](https://github.com/aaubs/ds23/edit/master/content/m6/L1/joke_app.py) is a simple streamlit app that uses IPA to print jokes
- EXTRA: [api_weather.py](https://github.com/aaubs/ds23/edit/master/content/m6/L1/api_weather.py) exercise from the class



## Database

<p align="center">
  <img src="images/schema.jpg" alt="Schema" width="400"/>
</p>


- [db_create.py](https://github.com/aaubs/ds23/edit/master/content/m6/L1/db_create.py) reads in excel file and transform it into SQL database
- [db_queries.py](https://github.com/aaubs/ds23/edit/master/content/m6/L1/db_queries.py) contains a few query examples
- [db_add_datapoints.py](https://github.com/aaubs/ds23/edit/master/content/m6/L1/db_add_datapoints.py) add new transactions
- [db_add_columns.py](https://github.com/aaubs/ds23/edit/master/content/m6/L1/db_add_columns.py) add new columns
- [data/Online Retail.xlsx](https://archive.ics.uci.edu/dataset/352/online+retail) is dataset used to create database