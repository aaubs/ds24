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

```python

# Import necessary libraries
import streamlit as st
import pandas as pd
import altair as alt
import matplotlib.pyplot as plt
import seaborn as sns

# Function to load the dataset
@st.cache_data  # Cache the function to enhance performance
def load_data():
    # Define the file path
    file_path = 'https://raw.githubusercontent.com/aaubs/ds-master/main/apps/M1-attrition-streamlit/HR-Employee-Attrition-synth.csv'
    
    # Load the CSV file into a pandas dataframe
    df = pd.read_csv(file_path)

    # Create age groups and add as a new column
    bin_edges = [18, 25, 35, 45, 60]
    bin_labels = ['18-24', '25-34', '35-44', '45-60']
    df['AgeGroup'] = pd.cut(df['Age'], bins=bin_edges, labels=bin_labels, right=False)

    return df

# Load the data using the defined function
df = load_data()

# Set the app title and sidebar header
st.title("Employee Attrition Dashboard 😊📈")
st.sidebar.header("Filters 📊")

# Introduction

# HR Attrition Dashboard

st.markdown("""
            Welcome to the HR Attrition Dashboard. In the backdrop of rising employee turnovers, HR departments are stressing the significance of predicting and understanding employee departures. Through the lens of data analytics, this dashboard unveils the deeper causes of employee churn and proposes strategies to boost employee retention.
""")
with st.expander("📊 **Objective**"):
                 st.markdown("""
At the heart of this dashboard is the mission to visually decode data, equipping HR experts with insights to tackle these queries:
- Which company factions face a greater likelihood of employee exits?
- What might be pushing these individuals to part ways?
- Observing the discerned trends, what incentives might hold the key to decreasing the attrition rate?
"""
)
                             
# Tutorial Expander
with st.expander("How to Use the Dashboard 📚"):
    st.markdown("""
    1. **Filter Data** - Use the sidebar filters to narrow down specific data sets.
    2. **Visualize Data** - From the dropdown, select a visualization type to view patterns.
    3. **Insights & Recommendations** - Scroll down to see insights derived from the visualizations and actionable recommendations.
    """)


# Sidebar filter: Age Group
selected_age_group = st.sidebar.multiselect("Select Age Groups 🕰️", df['AgeGroup'].unique().tolist(), default=df['AgeGroup'].unique().tolist())
if not selected_age_group:
    st.warning("Please select an age group from the sidebar ⚠️")
    st.stop()
filtered_df = df[df['AgeGroup'].isin(selected_age_group)]

# Sidebar filter: Department
departments = df['Department'].unique().tolist()
selected_department = st.sidebar.multiselect("Select Departments 🏢", departments, default=departments)
if not selected_department:
    st.warning("Please select a department from the sidebar ⚠️")
    st.stop()
filtered_df = filtered_df[filtered_df['Department'].isin(selected_department)]

# Sidebar filter: Monthly Income Range
min_income = int(df['MonthlyIncome'].min())
max_income = int(df['MonthlyIncome'].max())
income_range = st.sidebar.slider("Select Monthly Income Range 💰", min_income, max_income, (min_income, max_income))
filtered_df = filtered_df[(filtered_df['MonthlyIncome'] >= income_range[0]) & (filtered_df['MonthlyIncome'] <= income_range[1])]

# Sidebar filter: Job Satisfaction Level
satisfaction_levels = sorted(df['JobSatisfaction'].unique().tolist())
selected_satisfaction = st.sidebar.multiselect("Select Job Satisfaction Levels 😊", satisfaction_levels, default=satisfaction_levels)
if not selected_satisfaction:
    st.warning("Please select a job satisfaction level from the sidebar ⚠️")
    st.stop()
filtered_df = filtered_df[filtered_df['JobSatisfaction'].isin(selected_satisfaction)]

# Displaying the Attrition Analysis header
st.header("Attrition Analysis 📊")

# Dropdown to select the type of visualization
visualization_option = st.selectbox(
    "Select Visualization 🎨", 
    ["Attrition by Age Group", 
     "KDE Plot: Distance from Home by Attrition", 
     "Attrition by Job Role", 
     "Attrition Distribution by Gender", 
     "MonthlyRate and DailyRate by JobLevel"]
)

# Visualizations based on user selection
if visualization_option == "Attrition by Age Group":
    # Bar chart for attrition by age group
    chart = alt.Chart(filtered_df).mark_bar().encode(
        x='AgeGroup',
        y='count()',
        color='Attrition'
    ).properties(
        title='Attrition Rate by Age Group'
    )
    st.altair_chart(chart, use_container_width=True)

elif visualization_option == "KDE Plot: Distance from Home by Attrition":
    # KDE plot for Distance from Home based on Attrition
    plt.figure(figsize=(10, 6))
    sns.kdeplot(data=filtered_df, x='DistanceFromHome', hue='Attrition', fill=True, palette='Set2')
    plt.xlabel('Distance From Home')
    plt.ylabel('Density')
    plt.title('KDE Plot of Distance From Home by Attrition')
    st.pyplot(plt)

elif visualization_option == "Attrition by Job Role":
    # Bar chart for attrition by job role
    chart = alt.Chart(filtered_df).mark_bar().encode(
        y='JobRole',
        x='count()',
        color='Attrition'
    ).properties(
        title='Attrition by Job Role'
    )
    st.altair_chart(chart, use_container_width=True)

elif visualization_option == "Attrition Distribution by Gender":
    # Pie chart for attrition distribution by gender
    pie_chart_data = filtered_df[filtered_df['Attrition'] == 'Yes']['Gender'].value_counts().reset_index()
    pie_chart_data.columns = ['Gender', 'count']
    
    chart = alt.Chart(pie_chart_data).mark_arc().encode(
        theta='count:Q',
        color='Gender:N',
        tooltip=['Gender', 'count']
    ).properties(
        title='Attrition Distribution by Gender',
        width=300,
        height=300
    ).project('identity')
    st.altair_chart(chart, use_container_width=True)

elif visualization_option == "MonthlyRate and DailyRate by JobLevel":
    # Boxplots for MonthlyRate and DailyRate by JobLevel
    fig, ax = plt.subplots(1, 2, figsize=(15, 7))
    
    # MonthlyRate by JobLevel
    sns.boxplot(x="JobLevel", y="MonthlyRate", data=filtered_df, ax=ax[0], palette='Set2')
    ax[0].set_title('MonthlyRate by JobLevel')
    ax[0].set_xlabel('Job Level')
    ax[0].set_ylabel('Monthly Rate')

    # DailyRate by JobLevel
    sns.boxplot(x="JobLevel", y="DailyRate", data=filtered_df, ax=ax[1], palette='Set2')
    ax[1].set_title('DailyRate by JobLevel')
    ax[1].set_xlabel('Job Level')
    ax[1].set_ylabel('Daily Rate')
    
    plt.tight_layout()
    st.pyplot(fig)

# Display dataset overview
st.header("Dataset Overview")
st.dataframe(df.describe())


# Insights from Visualization Section Expander
with st.expander("Insights from Visualization 🧠"):
    st.markdown("""
    1. **Age Groups & Attrition** - The 'Attrition by Age Group' plot showcases which age brackets face higher attrition.
    2. **Home Distance's Impact** - The 'KDE Plot: Distance from Home by Attrition' visualizes if being farther away influences leaving tendencies.
    3. **Roles & Attrition** - 'Attrition by Job Role' reveals which roles might be more attrition-prone.
    4. **Gender & Attrition** - The pie chart for 'Attrition Distribution by Gender' provides insights into any gender-based patterns.
    5. **Earnings Patterns** - 'MonthlyRate and DailyRate by JobLevel' boxplots display the compensation distribution across job levels.
    """)

# Recommendations Expander
with st.expander("Recommendations for Action 🌟"):
    st.markdown("""
    - 🎁 **Incentive Programs:** Introduce incentives tailored for groups showing higher attrition tendencies.
    - 🏡 **Remote Work Options:** Providing flexibility, especially for those living farther from the workplace, could reduce attrition.
    - 🚀 **Training & Growth:** Invest in employee development, especially in roles with higher attrition rates.
    - 👫 **Gender Equality:** Foster an environment that supports equal opportunities regardless of gender.
    - 💸 **Compensation Review:** Regularly review and adjust compensation structures to stay competitive and retain talent.
    """)

``````

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