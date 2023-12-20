# Chat-with-PDF-Chatbot
This Chatbot is an interactive app developed to assist users to interact with their PDF. It is built using Open Source Stack. No OpenAI is required.

## Getting Started

Follow these steps to set up and run the project on your local machine.


## Create a Container LLM
```
docker --name chatbotimg 
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
<> Code > Local > Clone - Use Git or checkout with SVN using the web URL  -->  Copy URL
```
git clone https://github.com/Boite-a-Sable/Chat-with-PDF-Chatbot.git
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

---

### Using Private Git Repositories
In general, you do not want your server profiles to be public. Instead, you should persist your server profiles in private git repositories.

To use server profiles with private repositories, you must either:

Pull using HTTPS
Pull using SSH
For HTTPS with GitHub:

### Generate an access token in GitHub.
Specify the access token in the URL you assign to the SERVER_PROFILE_URL environment variable in your YAML files.
For SSH:

Include your keys and known hosts in the image under /home/ping/.ssh.

### Cloning from GitHub using HTTPS
Creating a GitHub Access Token\n

In GitHub, go to Settings --> Developer Settings --> Personal access tokens.

Click Generate new token and assign the token a name.
Grant the token privilege to the repo group.

Copy the token to a secure location. You won't be able to view the token again.

At the bottom of the page, click Generate Token.

### Using The Token In YAML
To use the token in your YAML file, include it in the SERVER_PROFILE_URL environment variable using this format:

https://<github-username>:<github-token>@github.com/<your-repository>.git
For example:

SERVER_PROFILE_URL=https://github_user:zqb4famrbadjv39jdi6shvl1xvozut7tamd5v6eva@github.com/pingidentity/server_profile.git
Using Git Credentials in Profile URL\n
Typically, variables in a SERVER_PROFILE_URL string are not replaced. However, certain Git user and password variables can be replaced.

To substitute for the user and password variables using values defined in your YAML files, include either or both ${SERVER_PROFILE_GIT_USER} and ${SERVER_PROFILE_GIT_PASSWORD} in your server profile URL. For example:

SERVER_PROFILE_URL=https://${SERVER_PROFILE_GIT_USER}:${SERVER_PROFILE_GIT_PASSWORD}@github.com/pingidentity/server_profile.git
When using layered server profiles, each layer can use the base user and password variables, or you can define values specific to that layer.

For example, for a license server profile layer, you can use the SERVER_PROFILE_LICENSE_GIT_USER and SERVER_PROFILE_LICENSE_GIT_PASSWORD variables, and substitute for those variables using values defined in your YAML files.

### Cloning using SSH
To clone using SSH, you can mount the necessary keys and known hosts files using a volume at /home/ping/.ssh, the home directory of the default user in our product images.
To clone from GitHub, you must add the necessary SSH keys to your account through the account settings page.

