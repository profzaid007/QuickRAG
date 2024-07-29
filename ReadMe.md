# QuickRAG - Localized RAG Model with Groq API

This project implements a localized Retrieval-Augmented Generation (RAG) model capable of processing PDFs, text files, and JSON files. It converts these documents into tokenized chunks, performs embeddings using transformer models, and leverages the Groq API for fast responses.

## Features

- **Document Types Supported**: PDF, text, and JSON
- **Tokenization**: Chunks text into segments of 1000 characters
- **Embeddings**: Uses Sentence Transformers and PyTorch for embeddings
- **LLM Interface**: Utilizes Groq API for efficient language model interaction

## Requirements

- Python 3.7+
- Required Python Packages:
  - `tkinter`
  - `PyPDF2`
  - `re`
  - `json`
  - `warnings`
  - `torch`
  - `sentence-transformers`
  - `groq`

## Setup

1. Clone the repository:

    ```bash
    git clone https://github.com/profzaid007/QuickRAG.git
    cd QuickRAG
    ```

2. Install the required packages:

    ```bash
    pip install tkinter PyPDF2 torch sentence-transformers groq
    ```

3. Set up your Groq API key:

    Obtain your API key from the Groq platform.
    Replace the placeholder API key in the `upload_docs.py` and `rag_model.py` files:

    ```python
    client = Groq(
        api_key="your_api_key_here",
    )
    ```

## Usage

### Step 1: Upload Documents

Run the `upload_docs.py` script to process your documents:

```bash
python upload_docs.py
```

Choose the type of file you want to upload:
1. PDF
2. Text
3. JSON

Follow the prompts to enter the file path.

### Step 2: Run the RAG Model

Run the `rag_model.py` script to interact with the RAG model:

```bash
python rag_model.py
```

Enter your question when prompted. The script will retrieve relevant context from the processed documents and provide a response using the Groq API.

## Script Details

### `upload_docs.py`

This script processes PDFs, text files, and JSON files, tokenizes them into chunks of 1000 characters, and saves them to `dataset.txt`.

### `rag_model.py`

This script performs the following tasks:

- Loads and encodes the dataset from `dataset.txt`
- Retrieves relevant context using embeddings
- Interacts with the Groq API to generate responses

## Example

### Uploading a PDF

```bash
Which type of file do you wish to use? Choose.
1. PDF - RAG
2. Text - RAG
3. JSON - RAG
Enter your option: 1
Enter the path of your data: /path/to/your/file.pdf
PDF Content appended to dataset.txt - each chunk on a separate line
```

### Asking a Question

```bash
Ask a question about your documents: What is the main topic of the document?
Context from RAG: 
[Relevant context from the document]

Groq Response: 
[Response from Groq API]
```

## Contributing

Feel free to submit issues or pull requests if you have any improvements or suggestions.