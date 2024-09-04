# Persian Text Search Engine - Information Retrieval Project

This repository contains the final project for an Information Retrieval (IR) course, focused on developing a search engine for Persian text. The project demonstrates essential steps in building a search engine, including text tokenization, normalization, stemming, and ranking based on TF-IDF weighted cosine similarity.

## Overview

The aim of this project is to develop a search engine capable of indexing and retrieving Persian language news articles. The search engine uses common information retrieval techniques such as:

- **Tokenization**: Breaking down text into individual words or tokens.
- **Text Normalization**: Ensuring consistency in the text data by removing or standardizing punctuation, spacing, and numbers.
- **Stemming**: Reducing words to their root forms, which helps in recognizing different forms of the same word.
- **TF-IDF**: Calculating the Term Frequency-Inverse Document Frequency (TF-IDF) score to weigh the importance of terms in each document.
- **Cosine Similarity**: Ranking documents by calculating the cosine similarity between the search query and the document vectors.

## Features

### 1. **Data Loading**
   - The search engine processes a JSON file (`IR_data_news.json`) that contains Persian news articles, including fields like:
     - `content`: The body of the news article.
     - `title`: The title of the news article.
     - `url`: A link to the original source of the article.

### 2. **Text Preprocessing**
   - **Tokenization**: The `tokenize()` function splits the text into tokens while handling special Persian punctuation and grammar rules, preparing the text for indexing.
   - **Normalization**: The `TextNormalizer` class handles:
     - Removing punctuation.
     - Correcting spacing issues, especially around Persian verb prefixes and suffixes.
     - Translating Arabic numerals to Persian numerals.
     - Ensuring consistent formatting across the dataset.

### 3. **Stemming**
   - Using the `parsivar` library, stemming is applied to reduce words to their base or root form, which is crucial for improving search accuracy by grouping similar words together.

### 4. **Search Functionality**
   - **Inverted Index**: The core of the search engine is an inverted index that maps terms (tokens) to the documents in which they appear.
   - **TF-IDF**: Term Frequency-Inverse Document Frequency (TF-IDF) is used to weigh the terms based on how important they are to a particular document, while discounting terms that appear too frequently across the corpus.
   - **Cosine Similarity**: The cosine similarity score is computed between the query and each document's vector representation (using TF-IDF weights), ensuring the ranking of documents based on their relevance to the query.

### 5. **Query Handling**
   - Users can input search queries in Persian, and the engine returns the most relevant documents (news articles) from the dataset.
   - **Top-K Results**: The engine returns the top-K most relevant documents by calculating the cosine similarity between the query and document vectors, using TF-IDF weighting for terms. The higher the cosine similarity, the more relevant the document is to the query.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/ArianQazvini/IR-SearchEngine.git
    cd IR-SearchEngine
    ```
2. Place the data file (`IR_data_news.json`) in the project root directory.

## Usage

1. **Running the Search Engine**:
    - Open and run the Jupyter notebook (`IR_Final_Proj_9931045.ipynb`).
    - The notebook will:
        - Load and preprocess the Persian news articles.
        - Build an inverted index.
        - Compute TF-IDF scores for each term.
        - Handle user queries and return the top search results based on cosine similarity between the query and document vectors.

2. **Example Queries**:
    - You can input queries in Persian to search the dataset and retrieve relevant articles along with their titles and URLs.

## Dependencies

The following libraries are used in this project:
- `parsivar`: A library for Persian language processing (tokenization, stemming).
- `numpy`: For numerical operations and data manipulation.
- `collections`: For building efficient data structures like inverted indexes.
- `re`: Regular expressions for text pattern matching.

Install them using:
```bash
pip install parsivar numpy
