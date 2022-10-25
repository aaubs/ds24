---
title: "NW Cases"
weight: 4
disableToc: true
draft: false
---

## Danish Power Elites

![](https://source.unsplash.com/GWe0dlVD9e0)

> Many people dream of being one of them, but only few make it all the way to the top. According to two CBS researchers, it takes more than just hard work to get to the top of the Danish hierarchy of power. [read more](https://www.cbs.dk/en/alumni/news/a-look-the-danish-power-elite)

In this project we are going to construct and explore a network of Danish power elites derived from boards of various organisations in th country.
We will construct an association network: Who is being in the same board? And first explore "basic" centrality indicators. Then identify communities and central persons within those. Finally we look at some "fancier" interactive network visualisation.


### Context: The Danish Power Elites

* [Antons PhD Thesis](https://magtelite.dk/wp-content/uploads/2015/09/Anton-Grau-Larsen-PhD-Elites-in-Denmark.pdf)
* [Brief Summary of findings (CBS)](https://www.cbs.dk/en/alumni/news/a-look-the-danish-power-elite)
* [Journal Paper in Sociology](https://journals.sagepub.com/doi/abs/10.1177/0038038512454349)
* More to be found with googleling...

### Data

* [Github (R Repository)](https://github.com/antongrau/eliter)
* [Magteliten website](https://magtelite.dk/data/)
* Or, easier... on [our github](https://github.com/SDS-AAU/SDS-master/raw/master/00_data/networks/elite_den17.csv)

### Tasks

* Who are the most central persons?
* Communities?
* What characterizes them?
* Link up with additional data?


## European AI Companies

![](https://source.unsplash.com/9SoCnyQmkzI) 

The [European AI Startup Landscape](https://www.ai-startups-europe.eu/) is a project that collects and catalogues AI-related startups in 5 European countries. We created a dataset based on webpages in the catalogue. In this data, we collected all URLs these companies link to on their websites.
This is a typical network structure, which can be explored to answer following questions:

- Which companies are most central players?
- Are there prominent suppliers / customers?
- Are there clusters or other agglomerations?

Before venturing into analysis, you will have to prepare the data (filter, clean up etc.)

We've prepared a starter notebook for you to get started: [👉 Starter EU AI companies](https://colab.research.google.com/github/aaubs/ds-master/blob/master/notebooks/M2_mapping_european_ai.ipynb)


## Notebooks

* [Starter EU AI companies](https://colab.research.google.com/github/SDS-AAU/DSBA-2022/blob/master/notebooks/M2_mapping_european_ai.ipynb)
* [Starter EU AI companies](https://colab.research.google.com/github/SDS-AAU/DSBA-2022/blob/master/notebooks/M2_mapping_european_ai-class.ipynb)
* [Python Magteliten Analysis](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M2_power_elites.ipynb)


## Resources

* https://gephi.org/ - Gephi: "Photoshop for networks"
* [Mapping Controversies](https://jacomyma.github.io/mapping-controversies/)

<!--
* [Python Magteliten Analysis](https://sds-aau.github.io/DSBA-2021/notebooks/M2_workshop_networks_R.nb.html)
-->