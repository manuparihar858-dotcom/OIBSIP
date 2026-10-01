# Autocomplete and Autocorrect Data Analytics

## Oasis Infobyte Data Analytics Internship — Level 2, Task 5

This project analyses autocomplete and autocorrect using classical NLP techniques.

The notebook builds:

- a cleaned text corpus
- frequency-based bigram autocomplete
- frequency-based trigram autocomplete
- edit-distance autocorrection
- a second autocorrection approach using a custom Levenshtein distance implementation
- precision and recall measurements
- prefix tests for autocomplete
- 20 deliberately misspelled-word tests
- word-frequency visualisation
- autocorrect outcome confusion matrix
- production-system limitations discussion

## Dataset

The notebook expects a plain-text corpus file:

```text
corpus.txt
```

The default documented source is Project Gutenberg public-domain text.

The raw corpus is not bundled because corpus size and licensing/source selection can vary. See `DATA_SOURCE.md`.

## NLP preprocessing

The notebook performs:

1. lowercasing
2. punctuation removal
3. tokenisation
4. stopword removal

Stopword removal is used for the statistical vocabulary and frequency analysis. The autocomplete model is built from the resulting token sequence, so predictions are intentionally a simplified educational implementation.

## Autocomplete

Two frequency-based approaches are compared:

### Bigram model

Predicts the next word from the immediately preceding word.

### Trigram model

Predicts the next word from the preceding two-word context.

For each test context, the notebook returns the top three predictions.

Autocomplete evaluation uses a held-out sequence of tokens. A prediction is counted as a hit when the actual next word appears among the returned top-k candidates.

## Autocorrect

Two approaches are compared:

1. Candidate generation using `pyspellchecker`.
2. A custom Levenshtein-distance candidate search over the corpus vocabulary.

Twenty deliberately misspelled words are evaluated against known intended words.

The notebook reports:

- correction accuracy
- correction precision
- correction recall
- correct/incorrect outcomes

For the binary evaluation used here, precision and recall are defined over successful exact corrections to the intended word.

## Visualisations

The notebook creates:

- bar chart of the 20 most frequent words
- confusion matrix showing correct and incorrect autocorrection outcomes

## Limitations

This project is intentionally a classical NLP implementation. Production keyboards use much richer signals, including language models, user history, context, personalization, multilingual modelling, candidate ranking, typo patterns, latency constraints, and continuously updated vocabularies.

The notebook is therefore an educational benchmark, not a production keyboard implementation.

## Project Structure

```text
DataAnalytics-L2-AutocompleteAutocorrect/
├── Autocomplete_Autocorrect_Analysis.ipynb
├── README.md
├── requirements.txt
└── DATA_SOURCE.md
```

## How to Run

```bash
pip install -r requirements.txt
```

Place the corpus file beside the notebook:

```text
corpus.txt
```

Then run:

```bash
jupyter notebook Autocomplete_Autocorrect_Analysis.ipynb
```

## Author

Devraj Parihar
