# Inequality Causes Extractor (rule-based NLP)

This project extracts and ranks frequent **stated causes of inequality** from a text corpus.
It searches for explicit causal markers in sentences (e.g., `because of`, `due to`, `driven by`, `caused by`), then normalizes the extracted fragments (tokenization, lemmatization, stopword removal) and aggregates them by frequency.

## What it does
- Reads `Corpus.txt`
- Splits text into sentences (NLTK)
- Keeps sentences that mention inequality-related keywords
- Extracts cause fragments using regular-expression patterns (causal markers)
- Normalizes extracted phrases (lemmas + stopwords removed)
- Produces a ranked list and saves it as CSV

## Input
- `Corpus.txt` — plain text file (English corpus)
> The corpus file is not included in the repository.

## Output
- `top_causes.csv` — table with columns:
  - `cause` — normalized cause phrase
  - `count` — frequency
  - `example` — one example sentence where the cause was found

(Optional) The script also plots a bar chart of the Top-30 causes.

## Requirements
Install dependencies:
```bash
pip install -r requirements.txt
```

## Run
1) Place `Corpus.txt` in the same folder as `inequality_causes.py`.
2) Run:
```bash
python inequality_causes.py
```

## Notes / Limitations
- This approach captures only explicitly stated causality via markers like because of / due to / ...
- Implicit causality (e.g., “X leads to Y”) may be missed.
- Output quality depends on the corpus and normalization settings (stopwords, fragment length).
