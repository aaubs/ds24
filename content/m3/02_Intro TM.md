---
title: "Intro to Transformer Models"
weight: 3
disableToc: true
draft: true
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

* [TM Applications - SBERT](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_Applications_SBERT_v1.ipynb)
* [TM Applications - HF](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_Applications_HF.ipynb)
* [Simple transformer LM](https://colab.research.google.com/github/jalammar/jalammar.github.io/blob/master/notebooks/Simple_Transformer_Language_Model.ipynb#scrollTo=BstYQU6NkkDA)
* [SBERT for Patent Search using PatentSBERTa in PyTorch](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M4_PatentSBERTa_For_PatentSearch.ipynb)

## Notebooks - FineTuning

* [TM FineTuning - SimpleTransformers](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_FineTuning_simpletransformer_v1.ipynb)
* [TM FineTuning - SBERT](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_FineTuning_SBERT_1.ipynb)
* [TM FineTuning - HF](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_2_Transformermodels_NLU_FineTuning_huggingface_2.ipynb)
* [SetFit Hatespeech vs bert and distilroberta](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebook/M3_2_SetFit_Hatespeech_%26_distilroberta_v4.ipynb)
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

| **Technique**                               | **Inventors & First Introduction (Year)**                                                                                                       | **Key / Best-Known Paper (Year)**                                                                                                          | **Notes / Additional Information**                                                                                                                                                                                                                                                                                                                                                                                                 |
|--------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Single Neuron / Perceptron**             | - **Frank Rosenblatt**: “The Perceptron: A Probabilistic Model…” (1958)                                                                                                               | - **Minsky & Papert**: *Perceptrons* (1969)                                                                                                                                        | - Rosenblatt’s perceptron was one of the earliest neural network models.<br>- Minsky & Papert (1969) highlighted its limitations, driving interest in multi-layer networks.<br>- Laid the foundation for feedforward neural networks.                                                                                                                                                                                               |
| **Multilayer Perceptron (MLP)**             | - **Paul Werbos**: (PhD Thesis, 1974) introduces backpropagation in theory                                                                                                             | - **Rumelhart, Hinton, Williams**: “Learning Representations by Back-Propagating Errors” (1986)                                                                                    | - Werbos’s thesis was not well-known initially.<br>- Rumelhart et al. (1986) popularized backpropagation, spurring the first wave of deep learning in the late 1980s–early 1990s.<br>- MLPs are fully connected feedforward networks used in classification, regression, etc.                                                                                                                                                       |
| **Recurrent Neural Network (RNN)**          | - **John Hopfield**: Hopfield Network (1982) introduced a form of recurrent computation                                                                                                | - **Jeffrey Elman**: “Finding Structure in Time” (1990)                                                                                                                            | - Hopfield networks (1982) are energy-based recurrent models.<br>- Elman networks showed how to capture temporal or sequential patterns (language, time-series).<br>- Other early RNN variants: Jordan networks (1986).                                                                                                                                                                                                           |
| **LSTM (Long Short-Term Memory)**           | - **Sepp Hochreiter & Jürgen Schmidhuber**: “Long Short-Term Memory” (1997)                                                                                                            | - **Gers, Schmidhuber, Cummins**: “Learning to Forget…” (1999)<br>- **Greff et al.**: “LSTM: A Search Space Odyssey” (2015)                                                         | - LSTMs introduced gating mechanisms (input, output, forget gates) to tackle vanishing/exploding gradients.<br>- Subsequent refinements (peephole connections, GRUs, etc.) improved sequence modeling.<br>- Achieved state-of-the-art performance on speech recognition, language modeling, and more.                                                                                                                                 |
| **CNN (Convolutional Neural Network)**      | - **Kunihiko Fukushima**: Neocognitron (1980)                                                                                                                                          | - **Krizhevsky, Sutskever, Hinton**: “ImageNet Classification with Deep Convolutional Neural Networks” (2012, a.k.a. AlexNet)                                                      | - Neocognitron was a precursor to modern CNNs.<br>- **Yann LeCun** refined CNNs in the late 80s–90s (e.g., LeNet for digit recognition).<br>- AlexNet’s success in 2012 sparked the modern deep learning revolution.<br>- CNNs became fundamental for image classification, detection, segmentation, etc.                                                                                                                                                                    |
| **Deep Belief Networks (DBN)**              | - **Geoffrey Hinton, Simon Osindero, Yee-Whye Teh**: “A Fast Learning Algorithm for Deep Belief Nets” (2006)                                                                           | - Same as first introduction paper; extended in subsequent works by Hinton et al.                                                                                                   | - DBNs stack Restricted Boltzmann Machines (RBMs) to learn hierarchical representations.<br>- One of the earliest successful “deep” models, trained greedily layer-by-layer.<br>- Revitalized interest in deep learning prior to the CNN breakthrough.                                                                                                                                                                         |
| **Autoencoders**                            | - Concept by **Rumelhart, Hinton, Williams** in the 1980s (parallel to MLP research), though not labeled “autoencoder” initially                                                       | - **Vincent et al.**: “Stacked Denoising Autoencoders” (2010)                                                                                                                      | - Autoencoders learn latent representations via reconstructing their inputs.<br>- Variants: denoising autoencoders, sparse autoencoders, contractive autoencoders.<br>- Used for unsupervised/self-supervised pretraining, dimensionality reduction, feature learning, etc.                                                                                                                                                     |
| **GNN (Graph Neural Network)**              | - **Marco Gori, Gabriele Monfardini, Franco Scarselli**: “A new model for learning in graph domains” (2005)                                                                           | - **Kipf & Welling**: “Semi-Supervised Classification with Graph Convolutional Networks” (2016)                                                                                    | - Scarselli et al. (2009) formalized the GNN framework.<br>- Kipf & Welling’s GCN (2016) popularized graph convolution, spurring a wave of GNN research (GraphSAGE, GAT, etc.).<br>- Used for social networks, molecule property prediction, recommendation systems, and more.                                                                                                                                                    |
| **Variational Autoencoder (VAE)**           | - **Diederik P. Kingma & Max Welling**: “Auto-Encoding Variational Bayes” (2013/2014)                                                                                                 | - **Rezende, Mohamed, Wierstra**: “Stochastic Backpropagation…” (2014)                                                                                                              | - VAEs introduce a latent-variable generative framework built around autoencoders.<br>- Widely used for image generation, anomaly detection, representation learning.<br>- Probabilistic approach to learning continuous latent spaces.                                                                                                                                                                                           |
| **Generative Adversarial Network (GAN)**     | - **Ian Goodfellow et al.**: “Generative Adversarial Nets” (2014)                                                                                                                     | - **Radford, Metz, Chintala**: “Unsupervised Representation Learning with Deep Convolutional GANs” (DCGAN, 2016)                                                                    | - GANs involve a generator and discriminator in a minimax game.<br>- DCGAN popularized stable training and improved image generation quality.<br>- Countless variants (WGAN, StyleGAN, CycleGAN) used for high-fidelity image synthesis, domain translation, etc.                                                                                                                                                                |
| **Transformer**                             | - **Vaswani, Shazeer, Parmar, Uszkoreit, Jones, Gomez, Kaiser, Polosukhin**: “Attention Is All You Need” (2017)                                                                       | - **Devlin et al.**: “BERT: Pre-training of Deep Bidirectional Transformers…” (2018)<br>- **Brown et al.**: “Language Models are Few-Shot Learners” (GPT-3) (2020)                  | - The Transformer removed recurrence and convolutions, relying on self-attention for sequence processing.<br>- BERT, GPT, T5, and other large Transformer models achieve state-of-the-art in NLP and beyond.<br>- Adaptations exist for vision (ViT), audio, multimodal tasks, etc.                                                                                                                                              |
