# DBRX RAG Implementation in Databricks

## Overview

This project demonstrates the implementation of a Retrieval-Augmented Generation (RAG) application using DBRX in a Databricks environment. The application leverages large language models (LLMs), embeddings, and tokenizers to provide intelligent and context-aware responses.

## Project Structure

The project structure consists of the following directories and files:

1. **DBRX_RAG_Implementation**: Root directory of the project.
2. **README.md**: Markdown file containing project information.
3. **resources**: Directory containing project resources.
    - **data**: Subdirectory for storing data files.
4. **src**: Source code directory.
    - **Load_component.ipynb**: Jupyter Notebook where LLM, embedding, and tokenizer are called.
    - **utils.ipynb**: Jupyter Notebook where the RAG class is defined.
    - **run.ipynb**: Jupyter Notebook responsible for running the RAG application.



## Requirements

Ensure you have the following prerequisites before running the application:

1. Databricks environment setup
2. Access to DBRX (Databricks Runtime for Machine Learning)
3. Necessary libraries installed (e.g., `transformers`, `faiss`, `langchain`)

## Setup Instructions

1. **Clone the Repository**:
    ```
    git clone <repository_url>
    cd DBRX_RAG_Implementation
    ```

2. **Upload to Databricks**:
    - Upload the `DBRX_RAG_Implementation` directory to your Databricks workspace.
    - Ensure the files are uploaded in the appropriate workspace folders.

3. **Load Data**:
    - Ensure the `sample_data.json` file is in the `resources/data` directory.
    - This data will be used for the RAG application.

4. **Run Notebooks**:
    - Open and run `Load_component.ipynb` to load the necessary components such as LLM, embeddings, and tokenizers.
    - Open and run `utils.ipynb` to define the RAG class and its methods.
    - Finally, open and run `run.ipynb` to execute the RAG application and see the results.

## File Descriptions

### resources/data/sample_data.json
This file contains the data required for the RAG application. Ensure your data is formatted correctly and placed in this directory.

### src/Load_component.ipynb
This notebook is responsible for loading the language model, embeddings, and tokenizer. Ensure you have the correct API keys and configurations set up.

### src/utils.ipynb
This notebook defines the RAG class and its methods. The class includes methods for retrieving documents and generating responses using the loaded LLM and embeddings.

### src/run.ipynb
This notebook runs the RAG application. It loads the data, initializes the RAG class, and processes the input queries to generate intelligent and context-aware responses.

## Usage

1. **Load Components**:
    - Run the `Load_component.ipynb` notebook to initialize the LLM, embeddings, and tokenizer.
    
2. **Define RAG Class**:
    - Run the `utils.ipynb` notebook to define the RAG class with necessary methods for retrieval and generation.

3. **Run the Application**:
    - Run the `run.ipynb` notebook to execute the RAG application. Provide your input queries and get context-aware responses.


---

Happy experimenting with RAG in Databricks!

