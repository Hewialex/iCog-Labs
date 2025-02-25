# Document Retrieval System

## Overview
This project implements a **TF-IDF-based document retrieval system** that allows users to search for the most relevant documents based on a query. It uses **cosine similarity** to rank documents based on relevance.

## Features
- Loads text documents from a specified directory.
- Uses **TF-IDF Vectorization** for feature extraction.
- Computes **cosine similarity** between queries and documents.
- Returns the top **k** most relevant documents.
- Supports **custom user queries** and example queries.

## Requirements
Ensure you have the following dependencies installed:

```bash
pip install numpy scikit-learn
```

## Usage

### 1. **Prepare Your Dataset**
- Extract your dataset into a folder (e.g., `/content/unzipped_data`).
- Ensure it contains **text files (`.txt`) or JSON files (`.json`)**.

### 2. **Run the Script**
Execute the script using:

```bash
python document_retrieval.py
```

### 3. **Search for Documents**
- Enter a **custom query** or use **default example queries**.
- The system will return the **top 3 most relevant documents** along with similarity scores and previews.

## Code Explanation

### **1. Load Dataset**
```python
def load_dataset(dataset_path):
```
- Reads **text files** from the dataset directory.
- Stores **file paths** and document content.

### **2. Compute TF-IDF Vectors**
```python
self.vectorizer = TfidfVectorizer(stop_words='english')
self.tfidf_matrix = self.vectorizer.fit_transform(documents)
```
- Converts documents into **TF-IDF vectors**.

### **3. Search and Rank Documents**
```python
def search(self, query, top_k=3):
```
- Computes **cosine similarity** between query and documents.
- Returns **top-k relevant documents**.

## Example Output
```
Enter your search query: machine learning

Query 1: 'machine learning'
--------------------------------------------------

Rank 1
Document: /content/unzipped_data/doc1.txt
Similarity Score: 0.7823
Preview: Machine learning is a subset of AI that enables systems to learn...
------------------------------

Rank 2
Document: /content/unzipped_data/doc2.txt
Similarity Score: 0.7312
Preview: Supervised learning and unsupervised learning are two main...
------------------------------
```

## Customization
- **Change `top_k` value** in `search()` to adjust the number of results.
- Add more **file types** (e.g., `.csv`) in `load_dataset()`.

## License
This project is **open-source** under the MIT License.

---

🚀 **Happy Searching!**
