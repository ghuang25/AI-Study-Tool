# Chat with Your Study Tool
## Description

This project allows you to interact with your study material, such as PDF articles, by uploading a document and asking questions. It leverages Streamlit for the user interface and Langchain with OpenAI's LLM for answering questions based on the provided text.

## Features

* Upload PDF documents
* Ask questions related to the uploaded document
* Get responses based on the text of the PDF using OpenAI's language model

## Installation
To get started, you need to install the required packages. Run the following commands in your terminal:

```
pip install openai langchain streamlit tiktoken pypdf chromadb
```

## Usage
1. **OpenAI API Key**: Ensure you have an OpenAI API Key. You will need this to interact with OpenAI's LLM.
2. **Run the application**: Use the command below to start the application:
```
streamlit run main.py
```
3. **Upload a PDF**: After the app launches, you can upload a PDF document by clicking the "Upload an Article" button.
4. **Ask a question**: Enter a question in the text input field. For example, you can ask for a summary or specific information from the document.
5. **Get a response**: Once you submit your question, the app will process the document and return an answer based on the contents of the uploaded file.

## How It Works
1. The PDF file is processed, and its text is extracted page by page using ```pypdf```.
2. The text is split into smaller chunks using **Langchain**'s ```CharacterTextSplitter```.
3. Embeddings are created using **OpenAI Embeddings** and stored in a vector database (Chroma).
4. **RetrievalQA** is used to retrieve relevant chunks of text and generate a response based on the user query.

## Notes
* This app requires a valid OpenAI API Key, which should start with ```sk-```.
* Ensure your API key is kept confidential and do not share it publicly.
