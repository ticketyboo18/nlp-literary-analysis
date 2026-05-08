# NLP-Based Literary Analysis of Classic Books

End semester project for the Natural Language Processing course

---

## Overview

This project implements a complete NLP pipeline on a multi-author classic books corpus. Starting from raw text, it covers preprocessing, structured retrieval, stylometric analysis, entity recognition, and unsupervised topic discovery.

---

## Pipeline

```
Raw Text → Preprocessing → Inverted Index → Boolean IR
                       ↓
              POS Analysis → Sentence Length → NER → LDA Topics
```

---

## Sections

**1. Environment Setup**
Installation of all required libraries and NLTK corpora.

**2. Dataset Loading**
Loads the [IsmaelMousa/books](https://huggingface.co/datasets/IsmaelMousa/books) dataset from HuggingFace. Train and validation splits are merged into a single DataFrame.

**3. Text Preprocessing**
- Lowercasing and truncation
- Word tokenization via NLTK
- Stopword removal
- POS-aware lemmatization using WordNet
- Type-Token Ratio (TTR) computed per author as a lexical richness metric

**4. Boolean Information Retrieval**
An inverted index maps each lemmatized term to the set of books containing it. Supports AND, OR, and AND NOT queries. Query terms are automatically lemmatized before lookup.

**5. POS Stylometric Analysis**
Per-author distribution of Nouns, Verbs, Adjectives, and Adverbs as a percentage of total tokens. Visualized as a grouped bar chart.

**6. Sentence Length Analysis**
Average sentence length, standard deviation, and sentence count computed per author using spaCy's sentence segmenter.

**7. Named Entity Recognition**
Entity type percentages (PERSON, GPE, LOC, ORG) and top-5 named persons extracted per book using spaCy's `en_core_web_sm` model.

**8. LDA Topic Modelling**
Unsupervised topic discovery using Gensim's LDA with K=5 topics. Full topic probability distribution shown per book. Interactive pyLDAvis visualization included.

---

## Tech Stack

| Library | Purpose |
|---|---|
| `datasets` | HuggingFace dataset loading |
| `nltk` | Tokenization, POS tagging, lemmatization |
| `spacy` | Sentence segmentation, NER |
| `gensim` | LDA topic modelling |
| `pyLDAvis` | Interactive topic visualization |
| `pandas` | DataFrame operations |
| `matplotlib` | POS distribution bar chart |

---

## How to Run

**Option 1 — Google Colab (recommended)**

Click the badge below to open directly in Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ticketyboo18/nlp-literary-analysis/blob/main/NLP_Literary_Analysis.ipynb)

Then go to **Runtime → Restart and Run All**.

**Option 2 — Local**

```bash
git clone https://github.com/ticketyboo18/nlp-literary-analysis.git
cd nlp-literary-analysis
pip install -r requirements.txt
python -m spacy download en_core_web_sm
jupyter notebook NLP_Literary_Analysis.ipynb
```

---


## Author

**[Your Name]**
B.Tech Electronics and Communication Engineering — Advanced Communication Technologies
Jaypee Institute of Information Technology, Noida
