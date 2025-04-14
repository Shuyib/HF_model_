[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Shuyib/HF_model_preview/HEAD)

# Car-ing is Sharing: LLM Model Review

![Car-ing is Sharing](car.jpeg)

## Project Overview

This project evaluates various Hugging Face large language models (LLMs) for a car dealership chatbot application called "Car-ing is Sharing". The chatbot is designed to assist customers and provide support to human agents through multiple NLP functionalities.

### Key Features

- **Sentiment Analysis**: Classify car reviews as positive or negative
- **Text Translation**: Translate customer reviews between English and Spanish
- **Question Answering**: Extract specific information from car reviews
- **Text Summarization**: Generate concise summaries of longer car reviews

## Project Structure

```
.
├── car.jpeg                   # Project image
├── Makefile                   # Build automation
├── notebook.ipynb             # Main analysis notebook
├── requirements.txt           # Project dependencies
└── data/
    ├── car_reviews.csv        # Car review dataset
    └── reference_translations.txt # Translation reference data
```

## Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd HF_model_review
```

2. Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

## Models Used

This project leverages several pre-trained models:

- **Sentiment Analysis**:
  - `distilbert-base-uncased-finetuned-sst-2-english`
  - `Qwen/Qwen2.5-1.5B-Instruct` (via API)

- **Translation**:
  - `Helsinki-NLP/opus-mt-en-es`

- **Question Answering**:
  - `deepset/minilm-uncased-squad2`

- **Summarization**:
  - `cnicu/t5-small-booksum`
  - `facebook/bart-large-cnn`

## Usage

1. Open the Jupyter notebook:

```bash
jupyter notebook notebook.ipynb
```

2. Run the cells to see model evaluations for:
   - Sentiment analysis with accuracy and F1 metrics
   - Translation quality with BLEU score calculation
   - Question answering capabilities
   - Text summarization quality

## API Access

For some models, you'll need to set up API access from huggingface.co. You can do this by creating a token on your Hugging Face account and setting it as an environment variable:

```bash
export HF_token="your_huggingface_token"
```

```python
import os
os.environ["HF_TOKEN"] = "your_huggingface_token"
```

## Development

This project includes a comprehensive Makefile with useful commands:

- `make install`: Set up the environment
- `make format`: Format code
- `make lint`: Lint code
- `make test`: Run tests
- `make clean`: Clean up environment

Run `make help` to see all available commands.

## Requirements

- Python 3.10 or higher (Used 3.11.9)
- See requirements.txt for Python dependencies:
  - transformers
  - evaluate
  - datasets
  - sentencepiece
  - openai
  - tenacity
  - ipykernel
  - torch

## License

[Creative Common License v1.0 Universal](https://github.com/Shuyib/HF_model_preview/blob/main/LICENSE)

## Acknowledgments

- Hugging Face for providing the model infrastructure
- Datasets are from [Datacamp projects](https://app.datacamp.com/learn/projects/2046)
- Special thanks to the teams behind the pre-trained models used in this project such as the Helsinki-NLP, Qwen team, and Facebook teams.
