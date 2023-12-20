# Chat-with-PDF-Chatbot
This Chatbot is an interactive app developed to assist users to interact with their PDF. It is built using Open Source Stack. No OpenAI is required.

## Getting Started

Follow these steps to set up and run the project on your local machine.


## Create a Container LLM
```
--namme chatbotimg 
```

```
pip install -r requirements.txt --default-timeout=100 future
```

```
sudo docker build -t chatbotimg .
```

```
docker images
```

Using Docker Desktop
```
docker run chatbotimg  
```

### Installation

<!--```sh -->
## Clone the repository
```
git clone <repository_url>
```

```
git clone https://github.com/Boite-a-Sable/Chat-with-PDF-Chatbot/
```

## Create the necessary folders
```
mkdir db
```

```
mkdir models
```

## Add your model files to the 'models' folder
```
mkdir docs
```

----
### Usage 

## Run the ingestion script to prepare the data

```
python ingest.py
```

## Start the chatbot application using Streamlit

```
streamlit run chatbot_app.py
```


### Video Ref.
Containerizing LLM-Powered Apps: Part 1 of the Chatbot Deployment
https://www.youtube.com/watch?v=7CeAJ0EbzDA

Deploy LLM Powered Apps on Azure App Service: Part 2 of the Chatbot Deployment
https://www.youtube.com/watch?v=vYIlhgVHAls
