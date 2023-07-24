**OPEN AI - API Data privacy:**
|
`Starting on March 1, 2023, we are making two changes to our data usage and retention policies:
OpenAI will not use data submitted by customers via our API to train or improve our models, unless you explicitly decide to share your data with us for this purpose. You can opt-in to share data.
Any data sent through the API will be retained for abuse and misuse monitoring purposes for a maximum of 30 days, after which it will be deleted (unless otherwise required by law).`|

**NOTE:** This repo was cloned from my private repo. Unfortuantely, I had sensitive info which meant I couldn't mirror the commits to this repo or make the private repo public. Happy to show the commits in my private repo on request. I managed to remove the commits with sensitive info and rearrange the git history, but unfortunately they persisted in GITHUB. Boo

- Remaining tasks to complete on this project:
    * Create option on web frontend to choose the directory on your local machine to upload files from
    * Add option to upload single files
    * Finish creating CI/CD pipeline for Docker images to be created following update to specific branch

## LLM / Embeddings
Using OpenAI LLM: OpenAI Davinci (GPT 3.5)
Embeddings: OpenAI Ada2


## data_loader.py 
Should be run independently when creating vectorstore indexes for the first time or when new files have been pushed to the documents directory

`$ python3 ./data_loader.py`

Variable - 
PERSIST set to TRUE will indicate that a vectorstore with indexes already exists
Note; if set to false, new vectorstore and indexes will be created

An OpenAI API KEY will be requested


## query_data.py
Loads the existing vectorstore to query data from

#Creates 'retriever' var to expose vectorstore indexes in a retriever interface.
#Uses 'RetrievalQA' API to send arguments such as user input to OpenAI API/LLM for a formatted response

NOTE: Now uses ConversationalRetrievalChain, sends user input to OpenAI API/LLM for a formatted response and follow up. 

Maintains chat history using streamlit's session persistence.

## Web Frontend
### app.py

Using streamlit python package to create and host the web frontend, rather than using command line to interact with the chatbot
This is the file which will expose/run the web frontend using streamlit. To start app, run;

```$ streamlit run appy.py```

An OpenAI API KEY will be requested before queries can be made.


## File structure and Document indexing
TBC - Chunks 1000, overlap 200


## Jupyter notebook
Included a ipynb for quick testing with RetrivalQA API for single QA on docs.


## requirements.txt
Essential py modules required for Langchain in Python VENV and Docker Image.