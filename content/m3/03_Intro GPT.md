---
title: "Intro to GPT Models"
weight: 5
disableToc: true
draft: false
---

![](http://jalammar.github.io/images/gpt2/gpt2-sizes-hyperparameters-3.png)

GPT models (Decoders) play a crucial role in generating subsequent words in tasks like text translation or story generation, providing outputs along with their probabilities. They utilize attention mechanisms twice during training: initially, Masked Multi-Head Attention, where only the beginning of a target sentence is revealed, and later, Multi-Head Attention, similar to encoders. In traditional transformer models, decoders interact with encoders by using the encoder's outputs to assist in tasks like sentence translation. However, GPT models adopt a unique approach by relying solely on a decoder, compensating for the absence of an encoder through extensive training on large datasets. This allows for embedding a vast amount of knowledge within the decoder. ChatGPT further advances these techniques by integrating human-labeled data to address issues such as hate speech and employing Reinforcement Learning for enhanced model quality.

## Notebooks - Basics

* [Generative Pre-trained Models - Basics](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_NLG_4.ipynb)
<!-- * [Generative Pre-trained Models - Basics - Solutions](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_NLG_4_Solutions.ipynb) -->

## Notebooks - Applications

* [TM Applications - LangChain](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_Into_LangChain_v1.ipynb)
* [TM Applications - LanceDB](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_LanceDB_v2.ipynb)
<!-- * [TM Applications - LanceDB - Solutions](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_LanceDB_v2_Solutions.ipynb) -->
* [TM Applications - RAG](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_NLG_3_RAG_Mistral_v2.ipynb)

## Notebooks - FineTuning

* [Prompt Engineering](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_NLG_prompt_engineering_v2.ipynb)
* [PEFT - LoRA](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M3_3_Finetune_opt_bnb_peft.ipynb)


## Resources

- [LangChain](https://python.langchain.com/docs/get_started/quickstart)
- [LanceDB - Vector database](https://lancedb.github.io/lancedb/)

## Flowiseai Framework ##

Here's a Simple Step-by-Step Tutorial for Installing Docker on Mac and Windows, and Running the `flowiseai/flowise:latest` Docker Image on Port 3000

---

### **Step 1: Install Docker**

#### **For Mac:**
1. **Download Docker Desktop:**
   - Visit [Docker Desktop for Mac](https://www.docker.com/products/docker-desktop/).
   - Download the version suitable for your Mac (Apple Silicon or Intel-based).

2. **Install Docker Desktop:**
   - Open the downloaded `.dmg` file.
   - Drag the Docker icon to your Applications folder.

3. **Start Docker:**
   - Open Docker Desktop from the Applications folder.
   - Follow the on-screen instructions to complete the setup.

4. **Verify Installation:**
   - Open the Terminal and run:
     ```bash
     docker --version
     ```
   - You should see the Docker version information.

#### **For Windows:**
1. **Download Docker Desktop:**
   - Visit [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop/).
   - Download the installer.

2. **Install Docker Desktop:**
   - Run the downloaded installer.
   - Follow the setup instructions. Ensure "Install required components for WSL 2" is selected.

3. **Start Docker:**
   - Open Docker Desktop.
   - Follow the setup process to configure Docker.

4. **Verify Installation:**
   - Open Command Prompt or PowerShell and run:
     ```bash
     docker --version
     ```
   - You should see the Docker version information.

---

### **Step 2: Pull and Run `flowiseai/flowise:latest` Image**

#### **1. Pull the Docker Image:**
   - Open a terminal or command prompt and run:
     ```bash
     docker pull flowiseai/flowise:latest
     ```

#### **2. Run the Docker Image:**
   - Run the following command to start the container on port `3000`:
     ```bash
     docker run -d -p 3000:3000 flowiseai/flowise:latest
     ```
   - Explanation:
     - `-d`: Runs the container in detached mode (in the background).
     - `-p 3000:3000`: Maps port 3000 of your machine to port 3000 in the container.

#### **3. Access Flowise AI:**
   - Open your web browser and go to:
     ```
     http://localhost:3000
     ```

---

