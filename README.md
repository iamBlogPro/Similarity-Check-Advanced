# Similarity-Check-Advanced
Checks for keyword similarity - then generates unique keywords and a color-coded spreadsheet with removed keywords, retained keywords and similarity.

# Keyword De-duplication with Agglomerative Clustering

This Python script helps you remove extremely similar keywords from a list using the Agglomerative Clustering algorithm. It leverages the power of sentence transformers to generate embeddings for each keyword and then clusters them based on similarity. The script also generates an Excel output file that shows which keywords were removed and their similarity to the retained keyword.

## Requirements

- Python 3.6 or higher
- Install required packages: `pip install -r requirements.txt`

## Usage

1. Place your list of keywords in a CSV file with no header (e.g., `keywords.csv`).

2. Run the script:

```bash
python deduplication.py
```

3. Follow the prompts to set the similarity threshold and output file name.

4. The script will generate two output files:
    - `unique_keywords.csv`: A list of unique keywords after removing similar ones.
    - `keywords_output.xlsx`: An Excel file with color-coded information on removed keywords, retained keywords, and their similarity.


## How does it work?

1. **Reads keywords from a CSV file** - The script reads your list of keywords from a CSV file, storing the keywords in a list.

2. **Generate keyword embeddings** - The script leverages the ```SentenceTransformer``` library to create embeddings for each keyword. Sentence transformers are pre-trained neural network models that can convert text into numerical vectors (embeddings) that capture semantic information. The script uses the ```paraphrase-distilroberta-base-v1``` model for this purpose.

3. **Compute similarity matrix** - The script calculates a similarity matrix for the keyword embeddings using the cosine similarity metric. Cosine similarity values range from 0 to 1. In this case, 0 would mean not similar at all - 1 would mean extremely similar. Try staying in the higher ranges.

4. **Perform Agglomerative Clustering** - Based on the similarity matrix, the script applies the Agglomerative Clustering algorithm to group similar keywords together. This algorithm creates a hierarchical clustering structure, merging pairs of clusters iteratively until the specified similarity threshold is reached.

5. **Set similarity threshold** - You can define a similarity threshold (default is 0.8) during the execution of the script. If the similarity between two keywords is higher than this threshold, they will be considered part of the same cluster and one of them will be removed.

6. **Generate output files** - The script creates two output files for you:

- ```unique_keywords.csv``` - Contains the list of unique keywords after removing similar ones.

- ```keywords_output.xlsx``` (or the name you entered) - An Excel file with color-coded information on removed keywords, retained keywords, and their similarity. Removed keywords are highlighted in yellow.
