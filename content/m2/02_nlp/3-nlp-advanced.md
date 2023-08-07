---
title: "NLP Applications Chatbot"
weight: 3
disableToc: true
draft: true
---

![](/ds22/images/viz-corgi-nlp3.png)
Roman x [Stable Diffusion](https://stability.ai/blog/stable-diffusion-public-release)

Chatbots are one of the most wide spread NLP applications. 
In this tutorial we will build a simple retrieval chatbot that can be used for example as an alternative for FAQ applications in companies.

The approach is following:
1. Train a model on variants of a question.
2. Take input and predict the type of question asked - this is called "intent"
3. Reply with a pre-defined response corresponding to the question asked.

Modern bots are more complex. They evaluate the whole (or large parts of the) dialogue. In addition some have the capacity to generate text.

The iput data looks like this:

{{%expand "👉 Expand to see JSON..." %}}
```json
{
  "intents": [
    {
      "tag": "greeting",
      "patterns": [
        "Hi",
        "Hey",
        "How are you",
        "Is anyone there?",
        "Hello",
        "Good day"
      ],
      "responses": [
        "Hey :-)",
        "Hello, thanks for visiting",
        "Hi there, what can I do for you?",
        "Hi there, how can I help?"
      ]
    },
    {
      "tag": "goodbye",
      "patterns": ["Bye", "See you later", "Goodbye"],
      "responses": [
        "See you later, thanks for visiting",
        "Have a nice day",
        "Bye! Come back again soon."
      ]
    },
    {
      "tag": "thanks",
      "patterns": ["Thanks", "Thank you", "That's helpful", "Thank's a lot!"],
      "responses": ["Happy to help!", "Any time!", "My pleasure"]
    },
    {
      "tag": "items",
      "patterns": [
        "Which items do you have?",
        "What kinds of items are there?",
        "What do you sell?"
      ],
      "responses": [
        "We sell coffee and tea",
        "We have coffee and tea"
      ]
    },
    {
      "tag": "payments",
      "patterns": [
        "Do you take credit cards?",
        "Do you accept Mastercard?",
        "Can I pay with Paypal?",
        "Are you cash only?"
      ],
      "responses": [
        "We accept VISA, Mastercard and Paypal",
        "We accept most major credit cards, and Paypal"
      ]
    },
    {
      "tag": "delivery",
      "patterns": [
        "How long does delivery take?",
        "How long does shipping take?",
        "When do I get my delivery?"
      ],
      "responses": [
        "Delivery takes 2-4 days",
        "Shipping takes 2-4 days"
      ]
    },
    {
      "tag": "funny",
      "patterns": [
        "Tell me a joke!",
        "Tell me something funny!",
        "Do you know a joke?"
      ],
      "responses": [
        "Why did the hipster burn his mouth? He drank the coffee before it was cool.",
        "What did the buffalo say when his son left for college? Bison."
      ]
    }
  ]
}
```
{{% /expand%}}

## Notebook

[{{< awesome fas fa-laptop-code >}} Training Chatbot](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M2_chatbot_train.ipynb)