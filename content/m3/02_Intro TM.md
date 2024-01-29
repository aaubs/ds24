---
title: "Intro to Transformer Models"
weight: 3
disableToc: true
draft: True
---


![](https://jalammar.github.io/images/transformer-ber-ulmfit-elmo.png)

## Literature

[Sutskever, I., Vinyals, O., & Le, Q. V. (2014). Sequence to sequence learning with neural networks. Advances in neural information processing systems, 27.](https://proceedings.neurips.cc/paper/5346-sequence-to-sequence-learning-with-neural-)

[Vaswani, A., Shazeer, N., Parmar, N., Uszkoreit, J., Jones, L., Gomez, A. N., ... & Polosukhin, I. (2017). Attention is all you need. Advances in neural information processing systems, 30.](https://proceedings.neurips.cc/paper/7181-attention-is-all)


[The illustrated transformer](https://jalammar.github.io/illustrated-transformer/)

[Simple transformer LM](https://colab.research.google.com/github/jalammar/jalammar.github.io/blob/master/notebooks/Simple_Transformer_Language_Model.ipynb#scrollTo=BstYQU6NkkDA)

   
## Notebooks - Basics

* [Transformer Models - Basics](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_v2.ipynb)

## Notebooks - Applications

* [TM Applications - SBERT](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_Applications_SBERT.ipynb)
* [TM Applications - HF](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_Applications_HF.ipynb)
* [Simple transformer LM](https://colab.research.google.com/github/jalammar/jalammar.github.io/blob/master/notebooks/Simple_Transformer_Language_Model.ipynb#scrollTo=BstYQU6NkkDA)
* [SBERT for Patent Search using PatentSBERTa in PyTorch](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M4_PatentSBERTa_For_PatentSearch.ipynb)

## Notebooks - FineTuning

* [TM FineTuning - SimpleTransformers](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_FineTuning_simpletransformer.ipynb)
* [TM FineTuning - SBERT](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_FineTuning_SBERT_1.ipynb)
* [TM FineTuning - HF](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_FineTuning_huggingface_1.ipynb)
* [SetFit Hatespeech vs bert and distilroberta](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_SetFit_Hatespeech_%26_distilroberta_v2.ipynb)
* [Seq2Seq - Neural Machine Translation](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M4_PyTorch_Seq2seq.ipynb)


## Slides - Attention Mechanism

{{<gslides src="https://docs.google.com/presentation/d/e/2PACX-1vT8Sv_I9OFiEq4cO_2LWvlJUdJl7wJlgOqf_7irlzp9J_s9jtKzfr3nxXn2j2PJ_Oz7shK7Mqzz_EUA/embed?start=false&loop=false&delayms=3000" >}}


## Slides - SBERT

{{<gslides src="https://docs.google.com/presentation/d/e/2PACX-1vRC0UpqCe7rDW_pqGPs4da76hjozk-Byz1k2tFlog0ZH1sMz3rsAN7cHZbWCwRVP5TsdfstRtK_OwnR/embed?start=false&loop=false&delayms=3000" >}}


### Classification with various vectorization approaches
* [TF-IDF and W2V Multi-Class Text Classification](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M4_TFIDF_W2V_multiclass_text_classification.ipynb)
* [BERT Multi-Class Text Classification](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M4_BERT_multiclass_text_classification.ipynb)
* [Implementing Multi-Class Text Classification LSTMs using PyTorch](https://colab.research.google.com/github/HamidBekamiri/ds-master/blob/main/notebooks/M4_LSTM_multiclass_text_classification_PyTorch_v1.ipynb)


## Resources

- OG SBERT-Paper [Reimers, N., & Gurevych, I. (2019). Sentence-bert: Sentence embeddings using siamese bert-networks. arXiv preprint arXiv:1908.10084.](https://arxiv.org/abs/1908.10084)
- [SBERT Docu](https://www.sbert.net)
- [NLP with SBERT](https://www.pinecone.io/learn/nlp/) - an ebook/course on the use of dense vectors (with SBERT for business applications)
- [SBERT-Training Tutorial](https://huggingface.co/blog/how-to-train-sentence-transformers)
- [BERTopic](https://maartengr.github.io/BERTopic/index.html) - a framework for topic modelling with SBERT embeddings
- [Milvus - Vector database](https://milvus.io)