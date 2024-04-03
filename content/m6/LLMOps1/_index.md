---
title: "Bonus Workshop: Using LLMs in your applications"
weight: 7
disableToc: true
draft: false
---

<!-- 
<p align="center">
  <img src="images/pen3.jpg" alt="" width="400"/>
</p>

-->


## Material

### Intro notebooks related to LLMs in code

- This notebook introduces to basic use of LLMs in code using together.ai as a backend.
[Intro to using LLMs via APIs](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M6_using_llm.ipynb)

- In the following we use the LLM to evaluate patent texts data using an LLM and create structured output. This approach can be used to extract useful information from messy data sources and process them further in predictive models or elsewhere.
[Using LLMs for data structuration - JSON output / function calling](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M6_LLMLabelSynthesis.ipynb)



### Building a simple chatbot API with LangServe and deployment on Huggingface Spaces using Docker

We are following the tutorial for the pirate-speak app from langserve: https://github.com/langchain-ai/langchain/blob/master/templates/README.md

We are changing up foolowing: 
- we use the `mistralai/Mixtral-8x7B-Instruct-v0.1` model and the prompt from the `langchain_together` package.
- we add api-key handling using .env files

The `server.py` file looks like this after adding the pirate-speak chain:

```python

from fastapi import FastAPI
from fastapi.responses import RedirectResponse
from langserve import add_routes
from pirate_speak.chain import chain as pirate_speak_chain

app = FastAPI()


@app.get("/")
async def redirect_root_to_docs():
    return RedirectResponse("/docs")


# Edit this to add the chain you want to add
add_routes(app, 
           pirate_speak_chain, 
           path="/pirate-speak",
           playground_type='chat')

if __name__ == "__main__":
    import uvicorn

    uvicorn.run(app, host="0.0.0.0", port=8000)

```

The `chain.py` file looks like this:

```python
#from langchain_community.chat_models import ChatOpenAI
from langchain_together import Together
from langchain_core.prompts import ChatPromptTemplate, MessagesPlaceholder

import os
from dotenv import load_dotenv
load_dotenv()
together_api_key = os.getenv("TOGETHER_API_KEY")

_prompt = ChatPromptTemplate.from_messages(
    [
        (
            "system",
            "You are an expert doctor. You believe that all diseases are formed by the consumption of cheese. No matter which disease or symptoms your patient presents with, you will believe that cheese is the cause of the disease. However, your treatment should all involve cheese. Cheese is both the cause of and solution to all problems. You should then lament that the medicine, cheese, will also cause more disease.",
        ),
        MessagesPlaceholder("chat_history"),
        
        ("human", "{text}"),
    ]
)
_model  = Together(
    #model="mistralai/Mistral-7B-Instruct-v0.2",
    model="mistralai/Mixtral-8x7B-Instruct-v0.1",
    temperature=0.7,
    top_k=50,
    top_p=0.7,
    repetition_penalty=1,
    together_api_key=together_api_key
)

# if you update this, you MUST also update ../pyproject.toml
# with the new `tool.langserve.export_attr`
chain = _prompt | _model
    
```

Once you have created the chain and added it to the app (server.py) you can run the app with the following command:

```bash
langchain serve
```
make sure that you are in an environment with langchain installed.

You can now access the playground at `http://localhost:8000/pirate-speak/playground` and test it out.
The API is available at `http://localhost:8000/pirate-speak/

You can use a RemoteRunnable to access the API from your code. Here is an example:

```python

from langserve.client import RemoteRunnable

# Initialize the RemoteRunnable with your API 
rag_app = RemoteRunnable("http://127.0.0.1:8000/rag-chroma/")

# call the API with a question
answer = rag_app.invoke("Tell me a joke!")

print(answer)

```

Optional:
You can test if the container is functional by running it locally.

```bash
docker build . -t YOUR-GREAT-NAME
```

```bash
docker run -p 8080:8080 -e PORT=8080 YOUR-GREAT-NAME
```

You can deploy on Huggingface Spaces as a Docker API
This requires that you start up a space on Huggingface and clone it into a repository on your local machine.

you will then have to copy all files from your project directory into this one. Make sure to not overwrite the README.md that comes from huggingface. It contains the instructions for the deployment that HF uses to start the container.

You will need to edit the dockerfile to include the together api key at build time. First add it to the secrets in the HF space. 
You also need to change up the uvicorn command (from the initial one created by langchain)


```Dockerfile
RUN --mount=type=secret,id=TOGETHER_API_KEY,mode=0444,required=true 

CMD ["uvicorn", "app.server:app", "--host", "0.0.0.0", "--port", "7860"]
```

Since we are adding new libraries to the project, you will need to add them to the pyproject.toml file. You can do this by editing the following lines - pydantic needs to be upversioned to 2.6.0 due to langchain_together requirements.

```toml
pydantic = "2.6.0"
rag-chroma = {path = "packages/rag-chroma", develop = true}
python-dotenv = "1"
langchain-together = "0.0.2.post1"
```

Now you should be able to push the changes to HF Spaces, which should trigger a build and deployment of the API. You can access the API at the URL provided by HF.