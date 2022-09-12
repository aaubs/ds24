---
title: "Rapid Prototyping with Streamlit"
weight: 6
disableToc: true
draft: false
---

![](https://aws1.discourse-cdn.com/business7/uploads/streamlit/original/2X/2/247a8220ebe0d7e99dbbd31a2c227dde7767fbe1.gif?height=200px)

Streamlit was first released in October 2019 and has gained enourmous popularity in the past year. The reason behind the framework's success is the ease with which it allows data scientists to build data driven web-apps without the need to deal with frontend development or other dev-ops stuff, while allowing to incorporate all kinds of functions going far beyond just dashboards. Going from a Jupyter Notebook to a Streamlit app just requires adding a few lines of code and rewriting a few smaller things.

## From ipynb to web-app

In this tutorial we will be going back to [{{< awesome fas fa-laptop-code >}} this Airbnb EDA Notebook](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1-airbnb-eda-geoplot-class.ipynb.ipynb) from last week and building a little web-app from it. 
**Plan of attack**
- We will isolate the data-prep and visualization parts we are interested in
- Build & test the app in uCloud
- Deploy the app via GitHub to the Streamlit Cloud (this step is optional, as you can also deploy via uCloud - ~2kr/day server costs)

{{% notice info %}}
[uCloud](https://cloud.sdu.dk) is a uninversity cloud service. You get 1000 DKK and 50GB storage to start with but can apply for more. This is usually granted, as the service is not used a lot. It's a great place to learn about modern platforms, infrastructure and more. You can play with different types of installations in a safe environment. You can also request very powerful machines.
{{% /notice %}}


<iframe src="https://rjuro-streamlit-prep-app-5xws2a.streamlitapp.com/" width="800" height="600" frameBorder="0"></iframe>