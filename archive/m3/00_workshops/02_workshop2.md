
---
title: Workshop 2 - Fun with Timeseries
weight: 3
disableToc: true
draft: false
---

![](/SDS-2021/images/tseries.png)

## Introduction 

### Context: LSTMS and timeseries


You have so far seen how RNNs are used for simle time series. In this workshop we will extend this to multi-step and simultaneusely multi-feature and multi-step situations.
Today we are going to make some money 💸 [^1]
We will be using financial data for that. There will be no time for backtesting however.




### 1. Build a baseline LSTM 
Build an LSTM net that predicts closing price changes 1 day ahead


### 2. Extend to multi-step 
Build an LSTM net that looks n timesteps back to predict the next period


### 3. Extend to multi-step and multi-feature
Build an LSTM that uses several inputs (e.g. other stocks or TA features)


## In class Notebooks

* R team [:::: HERE ::::](https://sds-aau.github.io/SDS-2021/workshops/2021/SDS_M3_workshop2_lstm.nb.nb.html)
* [{{< awesome fas fa-laptop-code >}} Py Team](https://colab.research.google.com/github/SDS-AAU/SDS-master/blob/master/M3/notebooks/Simple_LSTM_stock_prediction.ipynb)
* [{{< awesome fas fa-video >}} Python Team - Video](https://panopto.aau.dk/Panopto/Pages/Viewer.aspx?id=5839c4e0-ff75-4085-b961-ade300e65077)

[^1]: NO INVESTMENT ADVICE
  The Content is for informational purposes only, you should not construe any such information or other material as legal, tax, investment, financial, or other advice. Nothing contained on our Site constitutes a solicitation, recommendation, endorsement, or offer by AAUBS or any third party service provider to buy or sell any securities or other financial instruments in this or in in any other jurisdiction in which such solicitation or offer would be unlawful under the securities laws of such jurisdiction.
  All Content on this site is information of a general nature and does not address the circumstances of any particular individual or entity. Nothing in the Site constitutes professional and/or financial advice, nor does any information on the Site constitute a comprehensive or complete statement of the matters discussed or the law relating thereto. AAUBS is not a fiduciary by virtue of any person’s use of or access to the Site or Content. You alone assume the sole responsibility of evaluating the merits and risks associated with the use of any information or other Content on the Site before making any decisions based on such information or other Content. In exchange for using the Site, you agree not to hold AAUBS, its affiliates or any third party service provider liable for any possible claim for damages arising from any decision you make based on information or other Content made available to you through the Site.

<!---
{{< tabs >}}

{{< tab name="Joint recordings">}}
  <h2>Assignment 1 handout</h2>
  {{< panopto  "https://panopto.aau.dk/Panopto/Pages/Embed.aspx?id=4b2660d2-790f-49cf-84be-ada900ea3083&autoplay=false&offerviewer=true&showtitle=true&showbrand=false&start=0&interactivity=all" >}}

{{< /tab >}}



{{< tab name="R Application">}}
<div>

  <h2>R: Recording</h2>
 
 coming soon

</div>
{{< /tab >}}



{{< tab name="Python Application">}}
<div>
  
  
  <h2>Python group recoding </h2>
  {{< panopto "https://panopto.aau.dk/Panopto/Pages/Embed.aspx?id=3c6006e6-e8e2-4ac4-a0a8-ada900ea85bc&autoplay=false&offerviewer=true&showtitle=true&showbrand=false&start=0&interactivity=all" >}}
</div>
{{< /tab >}}

{{< /tabs >}}
 --->
