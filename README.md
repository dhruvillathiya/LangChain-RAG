# RAG Learning (Retrieval-Augmented Generation) — Project Overview

This repository demonstrates a Retrieval-Augmented Generation (RAG) setup for experimenting with document ingestion, vector storage, and retrieval-powered workflows.

## Contents

- [requirements.txt](requirements.txt) — Python dependencies.
- [pyproject.toml](pyproject.toml) — project metadata (optional / poetry).
- [src/\__init_.py](src/__init_.py) — project package initializer.
- Data:
  - [data/text_files/langchain_intro.txt](data/text_files/langchain_intro.txt)
  - [data/text_files/derivatives.txt](data/text_files/derivatives.txt)
  - [data/pdf/](data/pdf/) — source PDFs for ingestion.
- Vector store:
  - [vector_store/chroma.sqlite3](vector_store/chroma.sqlite3)
  - [vector_store/f1faf9af-ba28-49fe-8e6a-fcc2b5cb5bb2/](vector_store/f1faf9af-ba28-49fe-8e6a-fcc2b5cb5bb2/) — persisted embeddings/index files.
- Notebooks:
  - [notebook/pdf_loader.ipynb](notebook/pdf_loader.ipynb)
  - [notebook/document.ipynb](notebook/document.ipynb)

## Quickstart

1. Create and activate a virtual environment:

```sh
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS / Linux
source .venv/bin/activate
```

2. Install dependencies:

```sh
pip install -r [requirements.txt]
```

## Typical Workflow

- Place source documents in `data/pdf/` or `data/text_files/`.
- Run ingestion to convert PDFs/text into chunks and embeddings (notebooks).
- Persist embeddings to the local Chroma store (vector_store/chroma.sqlite3).
- Run retrieval + generation experiments.

## Notebooks

- Open the notebooks under notebook/ to inspect loaders and embedding examples:

`notebook/pdf_loader.ipynb` — PDF ingestion demo.
`notebook/document.ipynb` — interactive exploration.

## Tips

- If using a new machine, remove or back up `vector_store/chroma.sqlite3` to re-index from scratch.
- Keep secret keys and credentials out of the repo. Use `.env` (already present) for local secrets.
