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

