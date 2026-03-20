# IR Inverted Matrix Workshop

This repository contains a hands-on Information Retrieval (IR) workshop notebook focused on:

- Tokenization
- Text normalization (stop words + stemming)
- Inverted index
- Positional index
- Phrase query
- TF, IDF, and TF-IDF comparison

Main notebook: `IR_InvertedMatrix_Workshop.ipynb`

## Project Structure

- `IR_InvertedMatrix_Workshop.ipynb`: Complete workshop notebook
- `sample_docs/`: Input text documents used by the notebook
- `requirements.txt`: Python dependencies

## Prerequisites

- Python 3.10+ (recommended)
- VS Code with Jupyter extension, or Jupyter Lab/Notebook
- Internet connection (optional but useful for downloading RSS content and NLTK data)

## Setup (Windows PowerShell)

### 1. Clone and enter the project

```powershell
git clone git@github.com:liggiaelena/IR_inverted_Matrix.git
cd IR_inverted_Matrix
```

If you already have the folder locally, just open it in VS Code.

### 2. Create and activate a virtual environment

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```powershell
pip install --upgrade pip
pip install -r requirements.txt
```

## Run the Notebook

### Option A: VS Code (recommended)

1. Open the project folder in VS Code.
2. Open `IR_InvertedMatrix_Workshop.ipynb`.
3. Select the Python kernel from your `venv`.
4. Run cells from top to bottom.

### Option B: Jupyter Lab

```powershell
jupyter lab
```

Then open `IR_InvertedMatrix_Workshop.ipynb` and run all cells in order.

## Execution Order (Important)

Run cells in sequence because later sections depend on earlier outputs:

1. Document loading (`documents` list)
2. `tokenize(...)`
3. `normalize_tokens(...)`
4. Inverted/positional index creation
5. IDF calculation (`idf_scores`)
6. TF/TF-IDF comparison cells

If you run a later cell first, variables may be missing (for example: `documents`, `positional_index`, `idf_scores`).

## What You Should See

- Number of loaded documents
- Preview of tokens and normalized tokens
- Inverted index preview
- Phrase query matches
- Memory usage reports for positional index
- TF/IDF/TF-IDF tables (including `softwar` comparison)

## Common Issues and Fixes

### 1. `NameError` (variable not defined)

Cause: Cells executed out of order.
Fix: Run notebook from the first setup cells down to the current section.

### 2. NLTK stopwords error

Cause: NLTK data not downloaded.
Fix: Ensure the normalization cell runs successfully (it includes `nltk.download('stopwords', quiet=True)`).

### 3. Empty or low TF/TF-IDF values

Cause: Terms are stemmed in normalization.
Fix: Use stemmed query terms like `softwar` instead of `software`.

### 4. No documents loaded

Cause: `sample_docs/` is empty or path mismatch.
Fix: Verify files exist in `sample_docs/` and run document loading cell again.

## Quick Notes on Metrics

- `TF` counts how often a term appears in one document.
- `IDF` measures how rare the term is across all documents.
- `TF-IDF = TF * IDF`.

A higher TF-IDF generally means higher relevance of that term for that specific document.

## Optional: Minimal Install (if you do not want full requirements)

If you only need the notebook core logic, these are usually enough:

```powershell
pip install nltk pandas requests feedparser jupyter
```

## License

Workshop/educational use. Add a formal license if needed for distribution.
