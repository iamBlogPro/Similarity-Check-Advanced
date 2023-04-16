# Similarity-Check-Advanced
Checks for keyword similarity - then generates unique keywords and a spreadsheet with similar keywords and similarity

# Keyword De-duplication with Agglomerative Clustering

This Python script helps you remove extremely similar keywords from a list using the Agglomerative Clustering algorithm. It leverages the power of sentence transformers to generate embeddings for each keyword and then clusters them based on similarity. The script also generates an Excel output file that shows which keywords were removed and their similarity to the retained keyword.

## Requirements

- Python 3.6 or higher
- Install required packages: `pip install -r requirements.txt`

## Usage

1. Place your list of keywords in a CSV file with no header (e.g., `keywords.csv`).

2. Run the script:

```bash
python keyword_deduplication.py
