# RAG-based Chat Agent with LangChain and Gemini

This project implements a conversational AI agent that uses the Retrieval-Augmented Generation (RAG) pattern. It can answer questions based on the content of a webpage you provide. The agent is built using LangChain, Google's Gemini models, and is served through a Gradio chat interface.

## 🚀 Features

* **Web-based Knowledge**: Uses the content of any public webpage as its knowledge base.
* **Retrieval-Augmented Generation (RAG)**: The agent first retrieves relevant information from the provided webpage before generating an answer, which reduces hallucinations and provides more accurate responses.
* **Conversational Memory**: Remembers the context of the current conversation, allowing for follow-up questions.
* **Interactive UI**: A simple and user-friendly chat interface is provided using Gradio.
* **Powered by LangGraph**: The agent's logic is structured as a state graph, making the flow of control clear and easy to modify.

## 🛠️ How It Works

1.  **Data Ingestion**: The application fetches the content of a user-provided URL.
2.  **Indexing**: The text content is split into smaller chunks and stored in an in-memory vector store using Google's embedding models.
3.  **Retrieval**: When a user asks a question, the agent uses a `retrieve` tool to perform a similarity search on the vector store and find the most relevant text chunks.
4.  **Generation**: The retrieved context and the user's query are passed to the Gemini model, which generates a final, coherent answer.
5.  **State Management**: The entire process is managed by a `StateGraph` which orchestrates the decision of whether to retrieve information or generate a direct response.

## 📦 Installation

First, you need to install all the required Python libraries. You can do this by running the following command:

```bash
pip install "langchain[google-genai]" langchain-google-genai langchain-core langgraph langchain-community gradio ipywidgets
