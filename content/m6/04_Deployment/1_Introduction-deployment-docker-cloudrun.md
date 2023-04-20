---
title: "From notebook to containarized app in the cloud"
weight: 1
disableToc: true
draft: false
---

## Creating the Functionality

This tutorial guides you through building a simple cloud-based containerized app that provides entity anonymization functionality. The app is built using the FastAPI framework and Spacy library. The main functionality of the app is to take user text input, identify entities in the text using Spacy's pre-trained model, and then return the same text with the identified entities replaced by 'X'. The app includes a simple 'get' route that returns a message to confirm that the server is running. By following this tutorial, you will learn how to create a basic app using FastAPI, how to use Spacy for named entity recognition, and how to containerize the app using Docker.

Check out the repository here https://github.com/RJuro/anonymize_bds


the core function takes incoming text, identifies entities using spacy, and XXs them out using their start and end positions (given by spacy).


```python
def anonymize_text(text: str, model):
    # Use the Spacy model to parse the input text and extract named entities
    doc = model(text)

    # Create a list of dictionaries representing the identified entities
    entities = [
        {
            "start": ent.start_char,  # start position of the entity in the text
            "end": ent.end_char,  # end position of the entity in the text
            "type": ent.label_,  # type of the entity (e.g., PERSON, ORGANIZATION, etc.)
            "text": ent.text,  # actual text of the entity
        }
        for ent in doc.ents  # iterate over each named entity in the document
    ]

    # Create a copy of the input text as a list of characters
    anonymized_text = list(deepcopy(text))

    # Iterate over each identified entity and replace its characters with 'X'
    for entity in entities:
        start = entity["start"]  # start position of the entity in the text
        end = entity["end"]  # end position of the entity in the text
        anonymized_text[start:end] = "X" * (end - start)  # replace the entity's characters with 'X'

    # Convert the list of characters back into a string
    anonymized_text = "".join(anonymized_text)

    # Return a dictionary containing the identified entities and the anonymized text
    return {"entities": entities, "anonymized_text": anonymized_text}
```



when going from use of SpaCy in notebooks to an app, it is a good idea to have the model in the project directory. This can be done with `nlp.to_disk('models/en')`.

## Creating the API

To turn the function into a FastAPI route, we need to add a few things (not too many)

```python
@app.post("/anonymize", response_model=EntitiesOut)
def extract_entities(user_request: UserRequestIn):
```

We define the route but also the response_model and user_request using pydantic BaseModel.

## Running the API locally

The API can run locally using uvicorn:

`uvicorn app:app`

With that you can deploy the app on a virtual machine, considering requirements etc. By the way: Create a requirements.txt using `pipreqs`. Don't forget to add uvicorn to the requirements.

# Dockerizing the app

You can dockerize the app using a simple dockerfile in the same repository.

```yaml
# Use the official Python 3.9 image as the base image for the new Docker image
FROM python:3.9 

# Copy the contents of the current directory (the `.`) to the `/api` directory inside the Docker image
COPY . /api

# Install the Python packages listed in the `requirements.txt` file located in the `/api` directory
RUN pip install -r /api/requirements.txt

# Set the `PYTHONPATH` environment variable to the root directory inside the Docker container
ENV PYTHONPATH=/

# Set the working directory inside the Docker container to the root directory
WORKDIR /

# Expose port 8000 on the Docker container
EXPOSE 8000

# Specify that the entry point for the Docker container is the `uvicorn` command
ENTRYPOINT ["uvicorn"]

# Specify the default command to run when the container starts. This command starts the Uvicorn server, serving the `app` object in the `api.app` module, listening on all available network interfaces (`0.0.0.0`)
CMD ["api.app:app", "--host", "0.0.0.0"]
```

It is important to be careful with the relative paths. When loading the SpaCy model in the script for instance `model = spacy.load('api/models/en')` make sure to reference the model path relative to the pythonpath specified when creating the image.

You can now run the image using docker `docker build -t app .` the -t app is just giving it the name app.
Once the container is running, you can deploy the API.

## Push to Github and deploy

You can push the project folder to Github. Then go to goolge cloud platform (in this tutorial), select Cloud Run and the repository used. Make sure to provide the correct path to the dockerfile, which Cloud Run will use to create an Image. Important: don't forget to change the standard port 8080 to 8000. 
Cloud Run should than take care of the rest, creating the image and running your API in the serverless and scalable environment.