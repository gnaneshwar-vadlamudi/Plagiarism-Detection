# Transformers based Plagiarism Detection

This project implements a plagiarism detection system using the CORD-19 dataset and BERT embeddings. It can detect potential plagiarism in scientific articles related to COVID-19 across multiple languages.

## Sample Image

![image](https://github.com/gnaneshwar-vadlamudi/Plagiarism-Detection/assets/107243397/11c25dd3-5c08-43d8-934a-86d5d6e38fe0)

## Features

- Downloads and processes the CORD-19 dataset
- Creates BERT embeddings for article abstracts
- Supports plagiarism detection in multiple languages (English, French, German, Greek, Japanese, Russian)
- Translates non-English text to English for comparison
- Calculates cosine similarity between input text and existing articles
- Provides a plagiarism score and determination

## Prerequisites

- Python 3.6+
- Jupyter Notebook
- Kaggle API access (for downloading the CORD-19 dataset)

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/gnaneshwar-vadlamudi/Plagiarism-Detection
   ```

2. Install the required packages:
   ```
   pip install -r requirements.txt
   ```

3. Set up your Kaggle API credentials:
   - Place your `kaggle.json` file in the `~/.kaggle/` directory
   - Ensure the file has the correct permissions: `chmod 600 ~/.kaggle/kaggle.json`

## Usage

1. Open the Jupyter notebook in Google Colab and connect to a T4 GPU instance.

2. Run the cells in order to:
   - Download and preprocess the CORD-19 dataset
   - Create BERT embeddings for the articles
   - Set up the plagiarism detection function

3. To check a new article for plagiarism, use the `run_plagiarism_analysis` function:

   ```python
   new_incoming_text = "Your article text here..."
   analysis_result = run_plagiarism_analysis(new_incoming_text, vector_index, plagiarism_threshold=0.8)
   print(analysis_result)
   ```

## Customization

- Adjust the `plagiarism_threshold` in the `run_plagiarism_analysis` function to change the sensitivity of plagiarism detection.
- Modify the `language_list` to add or remove supported languages for translation.
