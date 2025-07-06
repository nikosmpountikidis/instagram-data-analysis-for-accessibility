# instagram-data-analysis-for-accessibility

A comprehensive workflow and toolkit for analyzing Instagram accounts and posts with a focus on accessibility for blind people or people with vision impairments. This repository provides scripts and Jupyter notebooks to:

* Collect data from Instagram using the Bright Data scraping service.
* Use and fine-tune language models for automated evaluation of accessible hashtags and descriptions.
* Analyze Alt Text and post metadata to measure accessibility compliance.
* Score key accessibility attributes, including alt text presence, readability, and hashtag conventions.


## Repository Structure

```text
instagram-data-analysis-for-accessibility-main/
├── LICENSE
├── README.md
├── alt_text_analysis.ipynb
├── get-data-through-bright-data.ipynb
├── scoring-each-attribute.ipynb
├── use-LLM-for-hashtags.ipynb
├── use-LLM-for-descriptions.ipynb
├── fine-tune-LLM-for-hashtags.ipynb
├── fine_tune_LLM_for_descriptions.ipynb
└── training-data/
    ├── hashtag-data.csv
    └── description-data.csv
```

- **`get-data-through-bright-data.ipynb`**: Workflow for scraping Instagram posts and account details via Bright Data.
- **`alt_text_analysis.ipynb`**: Analysis of alternative text (alt text) presence for each post.
- **`fine-tune-LLM-for-hashtags.ipynb`**: End-to-end fine-tuning pipeline for a multilingual model on the training-data/hashtag-data.csv labelled dataset (accessible vs. inaccessible hashtags).
- **`fine_tune_LLM_for_descriptions.ipynb`**: Fine-tuning pipeline for post descriptions using training-data/description-data.csv.
- **`use-LLM-for-hashtags.ipynb`**: Demonstrates how to use the trained LLM to evaluate hashtag accessibility according to PascalCase and readability rules.
- **`use-LLM-for-descriptions.ipynb`**: Demonstrates how to use the trained LLM to evaluate descriptions.
- **`scoring-each-attribute.ipynb`**: Aggregates metrics and assigns scores for accessibility attributes (alt text, hashtag format, description readability, etc.).

## Data Collection

- **Bright Data scraper**: Fetches Instagram account metadata (followers, posts, captions) and raw alt text when available.
- Outputs are stored as JSON/CSV for downstream analysis.

## Accessibility Analysis & Scoring

1. **Alt Text Analysis** (alt_text_analysis.ipynb):
    - Checks for presence of alt text on each post.
    - Analyzes if the text is written by AI or the user.

2. **Attribute Scoring** (scoring-each-attribute.ipynb):
    - Computes normalized scores for:
        - Alt Text Presence
        - Hashtag Conventions (PascalCase, length, character variety)
        - Description Readability (length, structure)
        - Other metrics (e.g., emoji usage, links).

##Model Fine-tuning

- **Hashtags**: Fine-tune a multilingual transformer (BERT) on training-data/hashtag-data.csv.
- **Descriptions**: Fine-tune for classification/regression on training-data/description-data.csv.

## LLM-based Evaluation & Generation

- **Hashtag Accessibility**: An LLM that is ready to be used to classify hashtags as Accessible/Inaccessible.
- **Description Accessibility**: An LLM for evaluation of post descriptions for readability and clarity.

Notebooks provide:
- Data preprocessing and tokenization.
- Training loops with LoRA/PEFT for efficient adaptation.
- Evaluation metrics and model saving/loading.

## Training Data

- **`training-data/hashtag-data.csv`**: A big dataset of hashtags labelled as accessible or inaccessible.
- **`training-data/description-data.csv`**: A big dataset of descriptions labelled as accessible or inaccessible.

## How to Use

1. Run data collection to update raw datasets.
2. Fine-tune models with the provided datasets or your updated training data if needed.
3. Use LLM evaluation notebooks to classify accessible text.
4. Execute analysis notebooks in order (alt_text, then scoring). 
5. Integrate into your pipeline or dashboard for ongoing accessibility monitoring.

## License

This project is licensed under the MIT License.
   
