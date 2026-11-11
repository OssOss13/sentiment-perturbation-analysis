# sentiment-perturbation-analysis

# Investigating the Effects of Negation and Contrastive Phrasing on Sentiment Classification

## Overview

This project investigates how negation and contrastive phrasing affect the predictions and confidence of a pretrained sentiment classification model.

We use DistilBERT, fine-tuned on the Stanford Sentiment Treebank (SST-2), without additional training or fine-tuning.

## Research Question

1. How does negation affect sentiment predictions?

## Dataset

- **SST-2:** [Stanford Sentiment Treebank](https://huggingface.co/datasets/stanfordnlp/sst2)

## Model

- **DistilBERT:** [distilbert-base-uncased-finetuned-sst-2-english](https://huggingface.co/distilbert/distilbert-base-uncased-finetuned-sst-2-english)

## Project Structure

- `notebooks/`: Experimental notebooks and analysis.
- `results/`: Experimental results.
- `figures/`: Generated visualizations.

## Methodology

The project is divided into two phases:

- **Phase I – Model Behavior:** Investigating changes in predictions and confidence under different linguistic perturbations.
- **Phase II – Model Interpretability:** Investigating influential words and internal representations.

## Installation

```bash
pip install -r requirements.txt
```

Open the notebook in `notebooks/` to reproduce the experiments.

## Team
Mohanad Osman
Omar Elsherif
Maral Mahshikian
Add team members here.
