# Persian Text Search Engine - Information Retrieval Project

This repository contains the final project for an Information Retrieval (IR) course, focused on developing a search engine for Persian text. The project demonstrates essential steps in building a search engine, including text tokenization, normalization, stemming, and ranking based on term frequency.

## Overview

The aim of this project is to develop a search engine capable of indexing and retrieving Persian language news articles. The search engine uses common information retrieval techniques such as:

- **Tokenization**: Breaking down text into individual words or tokens.
- **Text Normalization**: Ensuring consistency in the text data by removing or standardizing punctuation, spacing, and numbers.
- **Stemming**: Reducing words to their root forms, which helps in recognizing different forms of the same word.
- **Term Frequency**: Identifying the most frequent terms to assist in ranking search results.

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
   - **Ranking**: Documents are ranked based on term frequency, meaning that documents containing more occurrences of the search term are ranked higher in the search results.

### 5. **Query Handling**
   - Users can input search queries in Persian, and the engine returns the most relevant documents (news articles) from the dataset.
   - **Top-K Results**: The engine can return the top-K most relevant documents based on the frequency of query terms in each document.

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
        - Handle user queries and return the top search results based on term frequency.

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
