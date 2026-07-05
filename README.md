# AI-Research-Paper-Intelligence-Platform
# AI Research Paper Intelligence System

An NLP-powered system for semantic research paper retrieval, automated summarization, keyword extraction, and technical entity recognition using Transformer models.

---

# Overview

The rapid growth of scientific publications has made it increasingly difficult for researchers and students to discover relevant literature. Traditional keyword-based search engines often fail to capture the actual meaning behind a search query, resulting in less relevant recommendations.

This project addresses this challenge by developing an intelligent research paper analysis system that understands the semantic context of research articles. By combining Sentence Transformers, FAISS, and modern NLP techniques, the system enables users to search research papers semantically, generate concise summaries, extract meaningful keywords, and identify technical entities from research abstracts.

---

# Problem Statement

Finding relevant research papers among thousands of available publications is a time-consuming process. Researchers often spend significant time reading abstracts, identifying key concepts, and comparing multiple papers before finding useful information.

This project simplifies the research process by providing:

- Semantic search for relevant papers
- Automatic abstract summarization
- Keyword extraction
- Technical named entity recognition
- Intelligent research paper analysis

---

# Dataset

The project uses the **ML-ArXiv Papers Dataset** available on Hugging Face.

Dataset includes:

- Research Paper Titles
- Research Paper Abstracts

Dataset Link:

https://huggingface.co/datasets/CShorten/ML-ArXiv-Papers

---

# System Workflow

```text
Research Paper Dataset
        │
        ▼
Data Preprocessing
        │
        ▼
Sentence Embedding Generation
        │
        ▼
FAISS Vector Index
        │
        ▼
Semantic Search
        │
        ▼
Relevant Research Papers
        │
 ┌──────┼──────────────┐
 ▼      ▼              ▼
Summary Keywords     Entity Recognition
        │
        ▼
Research Paper Insights
```

---

# Features

## Data Preprocessing

The dataset is cleaned before generating embeddings.

Preprocessing steps include:

- Removing newline characters
- Removing unnecessary spaces
- Combining titles and abstracts into a single searchable document
- Preparing text for semantic embedding generation

---

## Sentence Embeddings

To capture the semantic meaning of research papers, the project uses the Sentence Transformer model:

```
all-MiniLM-L6-v2
```

Each research paper is converted into a dense vector representation, allowing semantically similar papers to be retrieved even when they do not share common keywords.

---

## Semantic Search

Semantic search is implemented using FAISS (Facebook AI Similarity Search).

The workflow includes:

- Generating embeddings for research papers
- Creating a FAISS vector index
- Performing nearest-neighbor search
- Retrieving the most relevant research papers

Example:

```python
search_papers("Deep Learning for Medical Image Analysis")
```

---

## Research Paper Summarization

Long research abstracts are summarized using the Transformer model:

```
facebook/bart-large-cnn
```

The generated summaries help users quickly understand the main contribution of each research paper.

Example:

```python
summarize_paper(abstract)
```

---

## Keyword Extraction

The project uses **KeyBERT** to extract important keywords and key phrases from research papers.

Example keywords:

- Deep Learning
- Medical Imaging
- Neural Networks
- Computer Vision
- Semantic Segmentation

Both single-word and multi-word key phrases are supported.

---

## Technical Named Entity Recognition

The project implements multiple approaches for extracting technical entities from research papers.

### Rule-Based Entity Recognition

A custom EntityRuler built with spaCy identifies predefined technical entities such as:

- Python
- TensorFlow
- PyTorch
- FastAPI
- FAISS
- BERT
- GPT
- spaCy

Recognized categories include:

- Programming Language
- Framework
- Library
- Model
- Vector Database

---

### Zero-Shot Entity Classification

A Transformer-based zero-shot classifier is implemented using:

```
facebook/bart-large-mnli
```

This approach predicts entity categories without requiring manually labeled training data.

Supported categories include:

- Model
- Framework
- Library
- Method
- Application
- Task
- Programming Language
- Vector Database

---

### Hybrid Entity Recognition

A hybrid approach combines rule-based matching with Transformer-based classification to improve the recognition of technical terminology commonly found in research papers.

Example entities include:

- Sentence Transformers
- KeyBERT
- Semantic Search
- Medical Image Analysis
- Named Entity Recognition
- Information Retrieval

---

# Technologies Used

- Python
- Pandas
- NumPy
- Sentence Transformers
- Hugging Face Transformers
- FAISS
- KeyBERT
- spaCy
- Scikit-learn
- Jupyter Notebook

---

# Project Structure

```text
AI-Research-Paper-Intelligence-System/
│
├── notebooks/
│   └── AI_Research_Paper_System.ipynb
│
├── data/
│
├── models/
│
├── requirements.txt
│
├── README.md
│
└── LICENSE
```

---

# How It Works

1. Load the research paper dataset.
2. Clean and preprocess the data.
3. Generate sentence embeddings.
4. Build a FAISS vector index.
5. Perform semantic search.
6. Retrieve relevant research papers.
7. Generate summaries.
8. Extract important keywords.
9. Identify technical entities.
10. Present research insights.

---

# Example Usage

### Search Research Papers

```python
search_papers("Natural Language Processing")
```

### Search and Summarize

```python
search_and_summarize("Machine Learning in Healthcare")
```

### Extract Keywords

```python
extract_keywords(text)
```

### Named Entity Recognition

```python
extract_entities(text)
```

---

# Learning Outcomes

Through this project, I gained practical experience in:

- Semantic Search
- Sentence Embeddings
- Vector Databases using FAISS
- Transformer-based Summarization
- Keyword Extraction
- Named Entity Recognition
- Zero-Shot Classification
- Information Retrieval
- End-to-End NLP Pipeline Development

---

# Future Enhancements

Future improvements for the project include:

- Developing a web application using Streamlit or FastAPI
- Supporting PDF upload for custom research paper analysis
- Implementing research paper recommendation systems
- Adding citation generation
- Comparing multiple research papers
- Integrating Retrieval-Augmented Generation (RAG)
- Improving entity recognition using domain-specific language models

---

# Note

The generated embedding files and FAISS index are excluded from this repository because of GitHub's file size limitations. These files are automatically created during execution of the notebook.

---

# Author

**Shubham Yadav**

B.Tech – Computer Science Engineering

Areas of Interest:

- Artificial Intelligence
- Machine Learning
- Natural Language Processing
- Information Retrieval
- Data Science

---

# Acknowledgement

This project was developed as part of my learning journey in Natural Language Processing and Information Retrieval. It demonstrates how semantic search, Transformer models, and vector similarity techniques can be combined to build an intelligent system for efficient research paper discovery and analysis.
