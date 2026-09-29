# Semantic Search Engine

A semantic search engine implementation in Python that leverages natural language processing and machine learning to enable intelligent text retrieval from large knowledge bases. This project combines text preprocessing, embedding generation, and similarity matching to provide meaningful search results based on semantic meaning rather than simple keyword matching.

## Features

- **Text Preprocessing**: Comprehensive text cleaning including tokenization, stopword removal, and lemmatization
- **Semantic Embeddings**: Converts text documents into semantic vectors for meaningful similarity comparisons
- **Large-scale Dataset Support**: Handles datasets with thousands of documents (50,000+ documents tested)
- **Knowledge Base Search**: Efficiently searches through categorical knowledge base documents
- **NLP-powered Retrieval**: Uses NLTK for advanced natural language processing

## Stack

- **Language**: Python 3
- **Runtime**: Google Colab (GPU-enabled with T4 acceleration)
- **Key Libraries**:
  - **pandas** - Data manipulation and analysis
  - **numpy** - Numerical computing
  - **nltk** - Natural language processing (tokenization, lemmatization, stopword removal)
  - **scikit-learn** - Machine learning and embedding generation (TF-IDF, Word2Vec, etc.)

## How It's Organized

```
Semantic_Search_Engine/
├── README.md                      # Project documentation
└── Semantic_Search_Engine.ipynb   # Main implementation notebook
    ├── Data Loading               # Upload and load CSV knowledge base
    ├── Text Preprocessing         # NLTK-based text cleaning
    ├── Embedding Generation       # Semantic vector creation
    ├── Similarity Matching        # Document retrieval
    └── Search Interface           # Query execution
```

### How It Works

The project follows a standard semantic search pipeline:

1. **Data Ingestion**: Loads a CSV knowledge base containing documents with fields like `document_id`, `category`, `title`, `content`, and `keywords`
2. **Text Preprocessing**: Combines text fields and applies cleaning (lowercasing, number removal, punctuation removal, tokenization, stopword removal, lemmatization)
3. **Vector Representation**: Converts preprocessed text into semantic embeddings
4. **Similarity Search**: Compares query embeddings with document embeddings to find the most relevant results
5. **Result Ranking**: Returns ranked documents based on semantic similarity scores

## How to Run It

### Prerequisites
- Google Colab account (recommended for GPU support)
- A CSV file with knowledge base documents containing at least: `title`, `content`, and `keywords` columns

### Steps

1. **Open the Notebook**:
   ```
   Upload Semantic_Search_Engine.ipynb to Google Colab
   ```

2. **Install/Download Dependencies**:
   - The notebook automatically downloads required NLTK packages:
     ```python
     nltk.download('punkt')          # Tokenizer
     nltk.download('stopwords')      # English stopwords
     nltk.download('wordnet')        # Lemmatizer
     nltk.download('omw-1.4')        # Open Multilingual Wordnet
     nltk.download('punkt_tab')      # Alternative tokenizer
     ```

3. **Upload Data**:
   - Run the cell with `files.upload()` to upload your CSV knowledge base
   - Expected format: columns for `document_id`, `category`, `title`, `content`, `keywords`

4. **Run Preprocessing**:
   - Execute text preprocessing cells to clean and prepare the data

5. **Generate Embeddings & Search**:
   - Create semantic embeddings for all documents
   - Execute query cells to perform semantic searches

### Example Dataset Structure

The notebook expects a CSV with this structure:

| document_id | category | title | content | keywords |
|---|---|---|---|---|
| KB000001 | Authentication | Unable to Access Your Login Password Step by Step | If you can no longer use your sign-in password... | password recovery, reset password, identity verification |
| KB000002 | Authentication | Login Troubleshooting the Easy Way | Problems with your log in are often caused by... | login not working, login error, technical issues |

### Performance Notes

- **Dataset Size**: Successfully tested with 50,000 documents
- **GPU Acceleration**: Uses T4 GPU in Google Colab for faster processing
- **Memory**: Dataset shape typically (50000, 5) for knowledge bases

## Try Asking

- **How do I improve the search relevance?** - Experiment with different embedding models (Word2Vec, FastText, BERT) or adjust preprocessing parameters
- **Can I use this with my own dataset?** - Yes, just format your CSV with `title`, `content`, and `keywords` columns and upload it
- **How do I deploy this as an API?** - Consider converting the notebook to a FastAPI/Flask application with the trained embeddings saved as pickle files

## Installation (Local Setup)

If running locally instead of Colab:

```bash
pip install pandas numpy nltk scikit-learn
python -m nltk.downloader punkt stopwords wordnet omw-1.4 punkt_tab
```

## Future Enhancements

- Integration with transformer-based embeddings (BERT, RoBERTa)
- Multi-language support beyond English
- Real-time search API deployment
- Persistent vector database (Pinecone, Weaviate, Milvus)
- User interface (Web or Desktop app)
- Query expansion and re-ranking strategies

## License

This project is provided as-is for educational and research purposes.

## Contributing

Contributions are welcome! Feel free to:
- Report issues or bugs
- Suggest improvements
- Submit pull requests with enhancements

---

**Created**: September 2026
**Repository**: [sakthiiiiiiii/Semantic_Search_Engine](https://github.com/sakthiiiiiiii/Semantic_Search_Engine)
