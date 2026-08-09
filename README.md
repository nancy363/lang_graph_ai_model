# lang_graph_ai_model
it is code of ai agent which reply questions and has tested on many questions
# Support Agent: Intelligent Retrieval & Generation System

This project implements an advanced, intelligent support agent built using LangGraph, designed to automate customer support inquiries. The agent utilizes a multi-step workflow including triage, cumulative retrieval, response generation, and an independent verification (judge) mechanism to ensure high-accuracy responses.  

## Key Features

* **Intelligent Triage:** Automatically classifies incoming questions into specific support categories or identifies them as out-of-scope.  
* **Cumulative Retrieval:** Uses a multi-round, context-aware retrieval strategy to gather relevant information from the knowledge base.  
* **Local Model Processing:** Leverages local Hugging Face models (`distilgpt2` for generation, `all-MiniLM-L6-v2` for embeddings, and cross-encoder for validation) to maintain data privacy and performance.  
* **Independent Judge:** Employs a Cross-Encoder to evaluate the quality of the generated answers, ensuring the agent provides accurate information.  
* **Robust Error Handling:** Includes automated validation for empty inputs and edge-case management.  

## Hugging Face Models Used & Their Purpose

* **all-MiniLM-L6-v2 (sentence-transformers):** Used for generating vector embeddings of user queries, category descriptions, and knowledge base paragraphs to perform semantic similarity matching and retrieval.
* **cross-encoder/ms-marco-MiniLM-L-6-v2 (cross-encoder):** Acts as an independent "Judge" to evaluate and score the semantic relevance and quality of the generated answers against the user's question.
* **distilgpt2 (transformers):** Used as the local causal language model pipeline to generate natural language response text based on the retrieved context and user prompt.

## System Requirements

This project was developed and tested within a Google Colab environment. The following hardware resources were utilized:  

* **System RAM:** 8.5 GB utilized out of 12.7 GB available.  
* **Disk Space:** 20.5 GB utilized out of 107.7 GB available.  
* **Hardware Acceleration:** GPU (e.g., T4) is highly recommended for faster model inference, embedding generation, and graph processing.  

## How to Run the Code

* **Environment Setup:** Ensure you are using a Python environment with GPU support (like Google Colab).  
* **Install Dependencies:** The code requires specific libraries. Run the following command first:
* pip install langgraph transformers sentence-transformers torch
Upload Files and Folders:

The script automatically generates a directory structure (/content/support-agent/data/knowledge_base) upon execution.

Crucial Step: Before running the main logic and test cases, ensure you upload your markdown (.md) knowledge base files and any required dataset files (such as sample_questions.json) into their respective folder paths so the program can read them successfully from disk.

Execution:

Copy the provided code into your notebook or IDE.

Initialize the LangGraph workflow.

Run the provided test cases block. The script will automatically process the questions, perform retrieval, generate answers, and verify them using the judge node.

View the generated langgraph_flow_diagram.jpg to visualize the agent's workflow.

Development Credits
Core Logic: Designed and implemented independently by the developer.

Code Assistance: Parts of the implementation were generated with the assistance of Gemini AI.

Environment: Built and validated on Google Colab.
