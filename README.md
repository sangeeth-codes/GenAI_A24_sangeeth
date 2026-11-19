# Assignment 24 -- Running a Local LLM with Ollama and LangSmith

## Overview

This assignment demonstrates how to run a Large Language Model (LLM)
locally using **Ollama**, connect to it through **LangChain**, send
prompts to the model, and track application execution using
**LangSmith**.

## Tools and Technologies

-   **Ollama** -- runs the language model locally.
-   **Llama 3.2 1B** (`llama3.2:1b`) -- the conversational model used in
    this assignment.
-   **LangChain** -- integrates the local model into the Python
    application.
-   **LangChain Ollama integration** (`langchain-ollama`) -- provides
    the `ChatOllama` wrapper.
-   **LangSmith** -- records and displays model execution traces.
-   **Python** and **Jupyter Notebook / VS Code** -- development
    environment.

## Assignment Tasks Completed

1.  Installed and ran Ollama locally.
2.  Downloaded the `llama3.2:1b` model using Ollama.
3.  Connected the model to Python using LangChain's `ChatOllama`
    wrapper.
4.  Sent prompts to the local model and printed its generated responses.
5.  Configured LangSmith tracing and verified that model runs appeared
    in the LangSmith project.
6.  Captured a screenshot of the LangSmith trace as assignment evidence.

## Project Files

``` text
GenAI_A24_sangeeth/
├── Assignment_24.ipynb
├── Screenshot 2026-11-19 at 12.28.38 PM.png
├── .gitignore
└── README.md
```

The `.env` file is intentionally excluded from Git because it contains
the LangSmith API key.

## Prerequisites

-   Python installed.
-   Ollama installed and running.
-   A LangSmith account and API key.
-   A Python virtual environment.

## Setup

### 1. Download the model

In Terminal, run:

``` bash
ollama pull llama3.2:1b
```

Check that the model is available:

``` bash
ollama list
```

### 2. Install the Python packages

Activate your project virtual environment, then install the integrations
used by the notebook:

``` bash
pip install -U langchain-ollama python-dotenv
```

### 3. Configure LangSmith

Create a `.env` file in the project folder and add your own LangSmith
API key:

``` text
LANGSMITH_TRACING=true
LANGSMITH_ENDPOINT=https://api.smith.langchain.com
LANGSMITH_API_KEY=your_langsmith_api_key
LANGSMITH_PROJECT=Assignment24-Ollama-Chatbot
```

Replace `your_langsmith_api_key` with your key. Do not commit or share
this file.

### 4. Run the notebook

Open `Assignment_24.ipynb` in VS Code or Jupyter Notebook and execute
the cells in order. The notebook initializes the local model, sends
prompts, displays responses, and enables LangSmith tracing.

The model is initialized using LangChain's `ChatOllama` wrapper with the
`llama3.2:1b` model.

## LangSmith Evidence

The screenshot included in this repository shows a successful
`ChatOllama` run in the LangSmith project:

-   **Project:** `Assignment24-Ollama-Chatbot`
-   **Model:** `llama3.2:1b`

It includes the recorded prompt, model response, and run details.

## Important Note

A local LLM runs on local hardware or local infrastructure rather than
requiring every prompt to be sent to a hosted model API. Model responses
can still contain errors or outdated information, so important outputs
should be independently verified.

## Repository

[GenAI_A24_sangeeth --
GitHub](https://github.com/sangeeth-codes/GenAI_A24_sangeeth)
