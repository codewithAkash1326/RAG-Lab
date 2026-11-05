# RAG Learning Notebooks

A small, hands-on project exploring the building blocks of retrieval-augmented generation (RAG): loading documents, splitting them into chunks, comparing vectors, and creating embeddings and an in-memory vector store.

## Project structure

```text
.
├── data/       # Sample text, JSON, CSV, and PDF documents
├── notebooks/  # Lessons, intended to be run in order
├── requirements.txt
└── docker-compose.yml
```

## Notebooks

1. `01_document_loading.ipynb` — load text, CSV, and PDF documents with LangChain.
2. `02_document_chunking.ipynb` — split documents into smaller overlapping chunks.
3. `03_cosine_simliarity.ipynb` — explore cosine similarity between vectors.
4. `04_embeddings_vector_store.ipynb` — generate Hugging Face or Cohere embeddings and use an in-memory vector store.

Run notebooks from the `notebooks/` directory so their relative paths to `../data/` resolve correctly.

## Setup

Use Python 3.10 or later. From the project root, create and activate a virtual environment, then install the dependencies:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python -m pip install jupyter
```

On macOS or Linux, activate the environment with `source .venv/bin/activate` instead.

Start Jupyter:

```powershell
python -m jupyter lab
```

Open the notebooks in order. The Hugging Face embedding model used in the final notebook is downloaded the first time it is run. Its Cohere section requires a `COHERE_API_KEY` environment variable in the notebook kernel; do not put API keys in notebook cells or commit them.

## Optional Qdrant service

The included `docker-compose.yml` defines a Qdrant service for local experiments. The current notebooks use an in-memory vector store, so Qdrant is not required to follow them.
