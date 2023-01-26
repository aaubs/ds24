---
title: "Group assignment 1"
weight: 4
disableToc: true
draft: false
---

Using a dataset of your choice from the first semester, build and train an ANN. Evaluate. Use gradio to build a simple interactive demo (in the notebook).

# Exercise 1: 

## Introduction


## Data: What do I get?

### Background


## Tasks

### 1. Create a network



### 2. Analysis

Make a little analysis on:

A: Network level characteristics. Find the overal network level of:

* Density
* Transistivity (Clustering Coefficient)
* Reciprocity

... for the different networks. Describe and interpret the results. Answer the following questions:

* Are relationships like friendship and advice giving usually reciprocal?
* Are friends of your friends also your friends?
* Are the employees generally more likely to be in a friendship or advice-seeking relationship?

B: Node level characteristics: Likewise, find out:

* Who is most popular in the networks. Who is the most wanted friend, and advice giver?
* Are managers in higher hirarchy more popular as friend, and advice giver?

C: Relational Characteristics: Answer the following questions:

* Are managers from the same 1. department, or on the same 2. hirarchy, 3. age, or 4. tenuere more likely to become friends or give advice? (hint: assortiativity related)
* Are friends more likely to give each others advice?


### 3. Visualization

Everything goes. Show us some pretty and informative plots. Choose what to plot, and how, on your own. Interpret the results and share some insights.

### Solution

*  [:::: HERE ::::](https://colab.research.google.com/github/SDS-AAU/SDS-master/blob/master/M2/notebooks/Solution_M2_A1.ipynb)


# Exercise 2: Crime Network

## Data

* In this exercise, you will analyze a crime network, which you will find in the following notebook:
* [Notebook: crime network](https://colab.research.google.com/github/aaubs/ds-master/blob/main/courses/ds4b-m2-1-nw/notebooks/s4-nw-2mode-exercise.ipynb)

## Tasks

First of all, construct the 2-mode network (code provided). Then, project it on th two modes, so that you end up with:

1. A network with persons as nodes, connected by jointly commited crimes
2. A network with crimes as nodes, connected by persons jointly commiting them.

Then, try to solve th following tasks:

* find the crime(s) that have the most shared connections with other crimes
* find the individual(s) that have the most shared connections with other individuals
* Which persons are implicated in the most number of crimes?

Then, there is also a bonus exercise which is a bit more complicated: 

* Find the people that can help with investigating a crime's person: Let's pretend that we are a detective trying to solve a crime, and that we right now need to find other individuals who were not implicated in the same exact crime as an individual was, but who might be able to give us information about that individual because they were implicated in other crimes with that individual.




 
