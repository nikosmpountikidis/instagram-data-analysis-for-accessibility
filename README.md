# instagram-data-analysis-for-accessibility

A comprehensive workflow and toolkit for analyzing Instagram accounts and posts with a focus on accessibility. This repository provides scripts and Jupyter notebooks to:

* Collect data from Instagram using the Bright Data scraping service.
* Analyze alt text and post metadata to gauge accessibility compliance.
* Score key accessibility attributes, including alt text presence, readability, and hashtag conventions.
* Use and fine-tune language models for automated evaluation and generation of accessible hashtags and descriptions.

## Repository Structure

instagram-data-analysis-for-accessibility-main/

├── LICENSE

├── README.md

├── get-data-through-bright-data.ipynb

├── alt_text_analysis.ipynb

├── fine_tune_LLM_for_descriptions.ipynb

├── fine-tune-LLM-for-hashtags.ipynb

├── use-LLM-for-descriptions.ipynb

├── use-LLM-for-hashtags.ipynb

├── scoring-each-attribute.ipynb

└── training-data/
    
    ├── hashtag-data.csv
    
    └── description-data.csv

`**get-data-through-bright-data.ipynb**`: Workflow for scraping Instagram posts and account details via Bright Data.

alt_text_analysis.ipynb: Analysis of alternative text (alt text) presence and characteristics for each post.

scoring-each-attribute.ipynb: Aggregates metrics and assigns scores for accessibility attributes (alt text, hashtag format, description readability, etc.).

use-LLM-for-hashtags.ipynb: Demonstrates how to leverage a pre-trained LLM (e.g., OpenAI GPT) to evaluate hashtag accessibility according to PascalCase and readability rules.

use-LLM-for-descriptions.ipynb: Uses an LLM to assess or generate accessible post descriptions.

fine-tune-LLM-for-hashtags.ipynb: End-to-end fine-tuning pipeline for a multilingual model on the training-data/hashtag-data.csv labelled dataset (accessible vs. inaccessible hashtags).

fine_tune_LLM_for_descriptions.ipynb: Fine-tuning pipeline for post descriptions using training-data/description-data.csv.
