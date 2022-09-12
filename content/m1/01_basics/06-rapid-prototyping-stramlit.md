---
title: "Rapid Prototyping with Streamlit"
weight: 6
disableToc: true
draft: false
---

![](https://aws1.discourse-cdn.com/business7/uploads/streamlit/original/2X/2/247a8220ebe0d7e99dbbd31a2c227dde7767fbe1.gif?height=200px)

Streamlit was first released in October 2019 and has gained enormous popularity in the past year. The reason behind the framework's success is the ease with which it allows data scientists to build data-driven web apps without the need to deal with frontend development or other dev-ops stuff while allowing them to incorporate all kinds of functions going far beyond just dashboards. Going from a Jupyter Notebook to a Streamlit app just requires adding a few lines of code and rewriting a few minor things.

## From ipynb to web-app

In this tutorial, we will be going back to [{{< awesome fas fa-laptop-code >}} this Airbnb EDA Notebook](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1-airbnb-eda-geoplot-class.ipynb.ipynb) from last week and building a little web-app from it. 

**Plan of attack**
- We will isolate the data-prep and visualization parts we are interested in
- Build & test the app in uCloud
- Deploy the app via GitHub to the Streamlit Cloud (this step is optional, as you can also deploy via uCloud - ~2kr/day server costs)

{{% notice info %}}
[uCloud](https://cloud.sdu.dk) is a uninversity cloud service. You get 1000 DKK and 50GB storage to start with but you can apply for more. This is usually granted, as the service is not used a lot. It's a great place to learn about modern platforms, infrastructure and more. You can play with different types of installations in a safe environment. You can also request very powerful machines.
{{% /notice %}}

<iframe allow="accelerometer; ambient-light-sensor; autoplay; battery; camera; clipboard-write; document-domain; encrypted-media; fullscreen; geolocation; gyroscope; layout-animations; legacy-image-formats; magnetometer; microphone; midi; oversized-images; payment; picture-in-picture; publickey-credentials-get; sync-xhr; usb; vr ; wake-lock; xr-spatial-tracking" sandbox="allow-forms allow-modals allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-downloads" height="auto" title="streamlitApp" src="https://rjuro-streamlit-prep-app-5xws2a.streamlitapp.com?embed=true" frameBorder="0" ></iframe>




### UCloud Set-up

For this project you will need 2 app-containers running: Coder-python and Streamlit. Both can run with minimal CPU/RAM requirements.
Streamlit can only run once you created a project in Code-python and saved an `app.py` file. It is a good idea, to create a public link and connect it to the streamlit-app. Thus, you can try out your app on your phone or share it.
Saving changes in `app.py` will trigger imediate recomplies and your app will update everywhere.

### Loading and preprocessing the data

We can just proceed as in a notebook, but it is useful to rewrite the data loading and preprocessing into a function and add the `@st.experimental_singleton` decorator. Streamlit performs a re-run every time something is chaged (UI) by the user e.g. a new filter is set. To reduce processing time it's a good idea not to re-run data-loading every single time.

```python
# LOAD DATA ONLY ONCE
@st.experimental_singleton
def load_data():
    data = pd.read_csv('http://data.insideairbnb.com/denmark/hovedstaden/copenhagen/2022-06-24/visualisations/listings.csv')

    # also preprocess as we did in the notebook
    data = data[data.number_of_reviews > 0]
    data = data[data.room_type.isin(['Private room', 'Entire home/apt'])]
    data['price_z'] = (data['price'] - data['price'].mean())/data['price'].std(ddof=0)
    data['price_z'] = data['price_z'].abs()
    data = data[data.price_z < 3]
    data['log_price'] = np.log(data['price'])

    return data

# LOAD THE DATA NOW!
data = load_data()
```

### Streamlit syntax and layout

Now, what do we need to turn our notebook into a web app?

```python

# 1. page-config

st.set_page_config(page_title='Streamlit - Dashboard 🤯',
                    page_icon="🚀",
                    layout='wide'
)

# 2. Page layout - e.g. a title

st.title("AirBnb rentals in Copenhagen 🇩🇰")

```

Streamlit layout follows your script - things that come first, will be displayed first...etc.


### The plots to be rendered

We will go for 2 plots. A geo-visualization using `pydeck` and a simple `altair` bar plot to show prices in different areas of town.

**Geoplot**

```python

layer = pdk.Layer(
        "ScatterplotLayer",
        data=data[['name','room_type','price', "longitude", "latitude"]].dropna(),
        pickable=True,
        opacity=0.7,
        stroked=True,
        filled=True,
        radius_scale=10,
        radius_min_pixels=1,
        radius_max_pixels=100,
        line_width_min_pixels=1,
        get_position=["longitude", "latitude"],
        get_radius=10*"log_price",
        get_color=[255, 140, 0],
        get_line_color=[0, 0, 0],
    )

# Set the viewport location
view_state = pdk.ViewState(latitude=data['latitude'].mean(), longitude=data['longitude'].mean(), zoom=12, pitch=50)

# Renders
r = pdk.Deck(layers=[layer], 
initial_view_state=view_state,
#map_style='mapbox://styles/mapbox/light-v9',
tooltip={"text": "{name}\n{room_type}\n{price}"}
)
```

**Altair barplot**

When using altair, we need to add one more thing, which is the number of processed observations. Altair doesn't want to process beyond 5000 observations. That means that you have two options. Either you limit your data, as we will do here, or you pre-computed things in e.g. `pandas`.
Here we will use 2 simple if-statements to make sure that data is always max 5000 observations.

```python
if len(data) > 5000:
    data_alt = data.sample(5000)

if len(data) <= 5000:
    data_alt = data

```
We use altair to create a bar chart and let it calculate the mean of the price variable (x-axis) with y and colours being split by the room type. We spread the chart across rows that represent neighbourhoods. Also, we add a tooltip that displays the values for the individual bars. We set strokeWidth to 0 to make things a bit tidier.

```python
price_chart = alt.Chart(data).mark_bar().encode(
    x='mean(price):Q',
    y=alt.Y('room_type:O',axis=alt.Axis(labels=False), title=" "),
    color=alt.Color('room_type:N', scale=alt.Scale(scheme='lightorange')),
    row='neighbourhood:N',
    tooltip=["neighbourhood:N", "mean(price):Q"]
).configure_view(strokeWidth=0).interactive()
```

### Introductin UI / Filters

We'll introduce 2 filters in the main page (you could also move them to the sidebar): price range and neighbourhood.
As you can see below, the `st.slider`and `st.multiselect` produce python objects (tuple and list) that we can use to filter our `data` DataFrame with plain Pandas.
e.g. When only 3 neighbourhoods are selected `neighbourhood_select` will turn a list of 3 elements and `data[data.neighbourhood.isin(neighbourhood_select)]` will result in a dataframe where only listings from these areas are present.

```python
#filter for price-range
price_selected = st.slider("Select price range", min_value = int(data.price.min()), max_value= int(data.price.max()), value = (300,3000), step=50)
data = data[(data.price > price_selected[0]) & (data.price < price_selected[1])]

#filter for neighborhoods
neighbourhood_select = st.multiselect('Select neighbourhoods', data.neighbourhood.unique(), data.neighbourhood.unique())
data = data[data.neighbourhood.isin(neighbourhood_select)]
```

### Rendering the visualizations
So far nothing is displayed. We only created the objects `r`(pydeck map) and `price_chart` altair chart. It's up to you how you like to handle it.
I find it a bit easier to separate compute and render parts.
Here we are going to add a horizontal column split (to make things a bit more pretty). We split the screen into 5 parts, where the first gets 3 and the second 2.
To display our chats, we use the streamlit functions `st.pydeck_chart` and `st.altair_chart`. You will find many more options in the [streamlit documentation](https://docs.streamlit.io/library/api-reference).

```python
row1_1, row1_2 = st.columns((3, 2))
with row1_1:
    st.pydeck_chart(r)

with row1_2:
    st.altair_chart(price_chart, use_container_width=False)
```

### Requirements
Our imports for that project look like this:

```python
import streamlit as st
import streamlit.components.v1 as components
import pydeck as pdk

import numpy as np
import pandas as pd 

import altair as alt

alt.renderers.set_embed_options(theme='dark')
```

In contrast to a notebook, we cannot really install packages on the fly. Considering a simple python deployment environment, we need to specify what packages (aside from streamlit) need to be installed so that the app can run.
This is often done by adding a `requirements.txt` file to the project folder. We add all libraries that we loaded just to be sure. This is not always the best idea, as things can clash... but that is a chapter of its own to be covered at a later point. 😵

```txt
altair
pydeck
numpy
pandas
streamlit
```
