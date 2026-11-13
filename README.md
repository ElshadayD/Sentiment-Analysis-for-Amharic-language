# Amharic Sentiment Analysis Using BERT

**Author:** Elshaday Desalegn  
**Institution:** Addis Ababa University  
**Date:** January 2025

## Overview

This project develops a binary sentiment classification model for Amharic text using a pretrained BERT model. It aims to classify Amharic tweets as positive or negative, addressing challenges associated with low-resource languages, linguistic variation, and limited annotated data.

## Dataset

Dataset: [`rasyosef/amharic-sentiment`](https://huggingface.co/datasets/rasyosef/amharic-sentiment)

The dataset contains labeled Amharic tweets:

- **Negative (0):** 1,189 training samples
- **Positive (1):** 1,026 training samples

| Split | Samples |
|---|---:|
| Train | 2,223 |
| Validation | 279 |
| Test | 279 |

## Methodology

**1. Text Preprocessing**
- Amharic orthographic normalization.
- Removal of URLs, emails, mentions, hashtags, emojis, and numbers.
- Filtering of very short texts.
- Character and punctuation normalization.

**2. Data Balancing**

SMOTE was applied to address class imbalance in the training data.

**3. Model**

Used [`rasyosef/bert-small-amharic`](https://huggingface.co/rasyosef/bert-small-amharic), a pretrained Amharic BERT model with approximately 27.8 million parameters, followed by a binary classification head.

**4. Training Configuration**

- Learning rate: 3e-5
- Batch size: 32
- Epochs: 10
- Optimizer: AdamW
- Maximum sequence length: 40

Fine-tuning was performed using the Hugging Face Trainer API.

## Results

The model was evaluated using accuracy, precision, recall, F1-score, and a confusion matrix.

<badge color="success">82.44% Test Accuracy</badge>

The model demonstrated promising performance in distinguishing positive and negative Amharic tweets, although sarcasm, informal expressions, and linguistic variation remain challenging.

## Technologies

Python · PyTorch · Hugging Face Transformers · Scikit-learn · Pandas · SMOTE

## Author

**Elshaday Desalegn**

[GitHub](https://github.com/ElshadayD) | [LinkedIn](https://www.linkedin.com/in/elsha-day/)
