# instagram-data-analysis-for-accessibility

A comprehensive workflow and toolkit for analyzing Instagram accounts and posts with a focus on accessibility. This repository provides scripts and Jupyter notebooks to:

* Collect data from Instagram using the Bright Data scraping service.
* Analyze alt text and post metadata to gauge accessibility compliance.
* Score key accessibility attributes, including alt text presence, readability, and hashtag conventions.
* Use and fine-tune language models for automated evaluation and generation of accessible hashtags and descriptions.

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
- **`alt_text_analysis.ipynb`**: Analysis of alternative text (alt text) presence and characteristics for each post.
- **`scoring-each-attribute.ipynb`**: Aggregates metrics and assigns scores for accessibility attributes (alt text, hashtag format, description readability, etc.).
- **`use-LLM-for-hashtags.ipynb`**: Demonstrates how to leverage a pre-trained LLM (e.g., OpenAI GPT) to evaluate hashtag accessibility according to PascalCase and readability rules.
- **`use-LLM-for-descriptions.ipynb`**: Uses an LLM to assess or generate accessible post descriptions.
- **`fine-tune-LLM-for-hashtags.ipynb`**: End-to-end fine-tuning pipeline for a multilingual model on the training-data/hashtag-data.csv labelled dataset (accessible vs. inaccessible hashtags).
- **`fine_tune_LLM_for_descriptions.ipynb`**: Fine-tuning pipeline for post descriptions using training-data/description-data.csv.

## Data Collection

- **Bright Data scraper**: Fetches Instagram account metadata (followers, posts, captions) and raw alt text when available.
- Outputs are stored as JSON/CSV for downstream analysis.

## Accessibility Analysis & Scoring

1. **Alt Text Analysis** (alt_text_analysis.ipynb):
    - Checks for presence of alt text on each post.
    - Analyzes length, keyword richness, and language.

2. **Attribute Scoring** (scoring-each-attribute.ipynb):
    - Computes normalized scores for:
        - Alt Text Presence
        - Hashtag Conventions (PascalCase, length, character variety)
        - Description Readability (length, structure)
        - Other metrics (e.g., emoji usage, links).

## LLM-based Evaluation & Generation

- **Hashtag Accessibility**: Uses prompt-based LLM calls to classify hashtags as Accessible/Inaccessible.
- **Description Accessibility**: Prompts LLM to evaluate or propose improvements to post descriptions for readability and clarity.

Both workflows include sample code and instructions for batched API calls.

##Model Fine-tuning

- **Hashtags**: Fine-tune a multilingual transformer (e.g., XLM-R) on training-data/hashtag-data.csv.
- **Descriptions**: Fine-tune for classification/regression on training-data/description-data.csv.

## Model Fine-tuning

- **Hashtags**: Fine-tune a multilingual transformer (e.g., XLM-R) on training-data/hashtag-data.csv.
- **Descriptions**: Fine-tune for classification/regression on training-data/description-data.csv.

Notebooks provide:
- Data preprocessing and tokenization.
- Training loops with LoRA/PEFT for efficient adaptation.
- Evaluation metrics and model saving/loading.

## Training Data

- **`training-data/hashtag-data.csv`**: Sample of hashtags labelled 1=accessible, 0=inaccessible.
- **`training-data/description-data.csv`**: Post descriptions labelled similarly for training the description classifier.

## How to Use

1. Run data collection to update raw datasets.
2. Execute analysis notebooks in order (alt_text, then scoring).
3. Use LLM evaluation notebooks to classify or generate accessible text.
4. Fine-tune models with your updated training data if needed.
5. Integrate into your pipeline or dashboard for ongoing accessibility monitoring.

## License

This project is licensed under the MIT License.
   
