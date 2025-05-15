# 🧩 Catan RAG Bot

## Project Description

This project enables semantic question answering on the *Catan* board game rulebook using Retrieval-Augmented Generation (RAG). Users can ask questions in natural language and receive accurate answers grounded in official game PDFs, powered by vector search and a large language model hosted by Groq.

---

## Name & URL

| Name                  | URL                                           |
|-----------------------|-----------------------------------------------|
| Embedding Model Page  | [Sahajtomar/German-semantic](https://huggingface.co/Sahajtomar/German-semantic) |
| Code                  | [GitHub Repository](https://github.com/dewiri/RAG-CATAN-BOT) |

---

## Data Sources

| Data Source | Description                        |
|-------------|------------------------------------|
| Catan PDFs  | Official english rulebook in PDF format |

---

## RAG Improvements

| Improvement        | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| Semantic Retrieval | Retrieves top-k semantically similar chunks using FAISS                     |
| LLM Augmentation   | Adds retrieved chunks as context to the Groq-hosted LLaMA 3 model            |
| Visualization      | UMAP projection with Matplotlib for embedding analysis                      |

---

## Chunking

| Type of Chunking                      | Configuration                                |
|--------------------------------------|----------------------------------------------|
| RecursiveCharacterTextSplitter       | 2000 characters per chunk, 200-character overlap |
| SentenceTransformersTokenTextSplitter| 128 tokens per chunk, no overlap             |

---

## Choice of LLM

| Name            | Link                                                                 |
|------------------|----------------------------------------------------------------------|
| Groq LLaMA 3 (70B)| [Groq LLaMA 3](https://groq.com/blog/llama3-now-available-on-groq/) |

---

## Test Method

- Manual test queries were created based on typical gameplay questions.
- Top-k retrieved chunks were reviewed for relevance.
- LLM answers were checked for alignment with official rules.

---

## Results

| Method                          | Retrieval Quality | Response Quality |
|----------------------------------|-------------------|------------------|
| Chunking + FAISS + Groq LLM     | High (top-5 match) | Accurate and fluent |
| UMAP Embedding Visualization    | Clear clustering   | —                |

---

## Example Usage

```python
run_qa_pipeline("How many players to play Catan?", k=5)
