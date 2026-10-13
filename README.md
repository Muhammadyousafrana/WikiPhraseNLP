# WikiPhraseNLP

## Overview

WikiPhraseNLP is a lightweight Python project for extracting meaningful noun phrases from Wikipedia article summaries using NLP tools such as `wikipedia`, `TextBlob`, and `fire`. It provides a simple command-line interface for quickly analyzing a topic and retrieving key phrases from its summary.

The project is designed to demonstrate how to combine data retrieval, text processing, and a Python CLI into a small but practical NLP workflow.

## Features

- Wikipedia article lookup and summary retrieval
- Noun phrase extraction using TextBlob
- Simple CLI powered by Python Fire
- Modular code structure for reusable NLP logic
- Test and quality automation with Makefile targets

## Project Structure

```
.
├── nlplogic/
│   ├── __init__.py
│   └── corenlp.py         # Core NLP logic: search, summary, phrase extraction
├── wikipedia_phrases.py   # CLI entry point using Fire
├── test_corenlp.py        # Core functionality tests
├── requirements.txt       # Python dependencies
├── Makefile               # Automation for install, test, lint, and format
├── .gitignore
└── README.md
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Muhammadyousafrana/NLP_project_with_python_Fire.git
   cd NLP_project_with_python_Fire
   ```

2. Install dependencies and required corpora:
   ```bash
   make install
   ```

   This step will:
   - upgrade `pip`
   - install required Python packages from `requirements.txt`
   - download the text corpora needed by TextBlob

## Usage

### Command-Line Interface

Extract noun phrases from a Wikipedia article directly from the terminal:

```bash
python wikipedia_phrases.py "Microsoft"
```

This command fetches the summary for the requested article and prints the noun phrases found in it.

### Programmatic Usage

You can also use the core logic in your own Python scripts:

```python
from nlplogic.corenlp import get_phrases

phrases = get_phrases("Microsoft")
print(phrases)
```

## Testing

Run tests with:

```bash
make test
```

Or directly with pytest:

```bash
pytest -vv --cov=nlplogic test_corenlp.py
```

## Code Quality

- Lint: `make lint`
- Format: `make format`

## Dependencies

Main dependencies include:

- textblob
- wikipedia
- nltk
- pattern
- fire
- pytest, pytest-cov
- black, pylint, click

Install everything with:

```bash
pip install -r requirements.txt
```

## Example Code

The main NLP logic lives in `nlplogic/corenlp.py` and includes functions for:
- searching Wikipedia
- fetching article summaries
- extracting noun phrases with TextBlob

The script `wikipedia_phrases.py` exposes `get_phrases` through a Fire-based CLI.

## Contributing

Feel free to open issues or submit pull requests if you would like to improve the project or suggest new features.
