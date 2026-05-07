# HSL748 Natural Language Understanding - Project by Rashmi Ijari (2024HCS7004)

This project compared subword tokenization algorithms (BPE, Unigram and Morfessor) on Marathi (a morphologically rich, low-resource agglutinating language). 

# Overview

This project builds, evaluates, and compares three tokenization approaches for Marathi NLP tasks:

- Byte Pair Encoding (BPE): trained with SentencePiece for greedy merging of frequent co-occuring morphemes
- Unigram Language Model:  also trained with SentencePiece for probabilistic subword segmentation
- Morfessor: an unsupervised morphological segmentation model

Evaluation is performed on both the Wikipedia training corpus and an independent Marathi news dataset from Kaggle, using intrinsic metrics (fertility score, characters per token, word fragmentation rate, unique vs shared tokens, vocabulary statistics) and qualitative evaluation of segmentations.

# Repository Contents

- HSL748_Project_Code (Final).ipynb   -  Code notebook (coded on Google Colab)
- README.md                           -  This file

# Pipeline 

1. Corpus construction: Marathi Wikipedia dump loaded via Hugging Face `datasets` (`wikimedia/wikipedia, 20231101.mr`)
2. Text normalisation: Unicode normalisation, stopword filtering, and cleaning of links, email IDs, HTML pages and so on. 
3. Tokenizer training: BPE and Unigram models trained via `sentencepiece`; Morfessor trained via the `morfessor` library
4. Intrinsic evaluation metrics: Fertility scores, Characters Per Token, Word Fragmentation Rate, vocabulary statistics, and overlapping tokens
5. Testing the trained tokenizers: All three tokenizers applied to the [Kaggle Marathi News Dataset](https://www.kaggle.com/datasets/disisbig/marathi-news-dataset)
6. Qualitative analysis: Side-by-side segmentation examples for the same sentences across models

# Libraries Used

The notebook is designed to run on Google Colab. The libraries used and their purposes are listed below:

- `datasets` (Hugging Face): for loading Marathi Wikimedia Wikipedia corpus 
- `sentencepiece`: for implementing BPE and Unigram tokenizer training
- `morfessor`: for unsupervised morphological segmentation (to compare its performance with BPE and Unigram)
- `kagglehub`: for downloading the Marathi news dataset
- `matplotlib`, `matplotlib_venn`: for plotting results 
- `pandas`: for tables 

# How to Run

1. Open `HSL748_Project_Code (Final).ipynb` in [Google Colab](https://colab.research.google.com/drive/1BjxuJy1QUPRLPbvq2NqZyY01Q6lHS-an?usp=sharing).
2. Run all cells in order
3. A Kaggle API token (`kaggle.json`) may be required for the news dataset download cell.
