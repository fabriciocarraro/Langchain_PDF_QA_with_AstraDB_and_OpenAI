# Langchain_PDF_QA_with_AstraDB_and_OpenAI

This repository demonstrates how to build a PDF Document Question Answering (QA) system using **Langchain**, **AstraDB (Cassandra)**, and **OpenAI**. The system extracts text from a PDF, generates vector embeddings, stores them in AstraDB, and allows querying of the content in a user-friendly question-answer format.

## Features
- **PDF Text Extraction**: Extracts content from a PDF document using `PyPDF2`.
- **Text Chunking**: Efficiently splits the PDF text into manageable chunks to work within OpenAI token limits.
- **Vector Embeddings**: Embeds text chunks using `OpenAIEmbeddings` and stores them in AstraDB for fast retrieval.
- **Question Answering**: Supports natural language querying of the document, returning the most relevant information.
- **Langchain Integration**: Utilizes Langchain's framework for managing LLMs, vector stores, and embeddings.

## Prerequisites
Before running this project, ensure you have the following:
- Python 3.7 or later
- Access to the following APIs:
  - OpenAI API (for embeddings and querying)
  - AstraDB (Cassandra) instance (for storing vector embeddings)

## Setup Instructions

1. Clone the Repository:
2. Install Dependencies:
3. Set Up Environment Variables:
   You'll need to set your environment variables for OpenAI and AstraDB:
   - `ASTRA_DB_APPLICATION_TOKEN`: Your AstraDB token.
   - `OPENAI_API_KEY`: Your OpenAI API key.

   You can set them in a `.env` file or in your environment directly.

4. Modify PDF Path:
   Update the path to your PDF file in the code:
   ```python
   pdfreader = PdfReader('/content/your_pdf_file.pdf')
   ```

5. Run the Notebook:
   Open and run the Jupyter Notebook to execute the code.

## Usage

1. **Ingest PDF Content**: The notebook will read the PDF, split the text into chunks, and store vector embeddings in AstraDB.
2. **Ask Questions**: You can ask natural language questions about the content of the PDF directly in the console. The system will retrieve the most relevant sections and provide answers based on the PDF data.

Example:

```
QUESTION: "Tell me about scaling laws in the Llama 3 paper"
ANSWER: "The Llama 3 paper discusses the use of scaling laws in their experiments..."
```

## Code Overview

### Key Components:
- **AstraDB**: Used as a vector store for fast retrieval of document chunks.
- **OpenAI API**: Provides embeddings and is used to answer natural language queries.
- **Langchain**: Orchestrates the embeddings, vector stores, and LLMs for building the document QA system.

## Contributing
Feel free to fork this repository, open an issue, or submit a pull request for any improvements, features, or fixes.
