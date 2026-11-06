# Flickr8k Multimodal NLP Project

## Overview

This project explores multimodal learning by combining Natural Language Processing (NLP) and Computer Vision using the Flickr8k dataset.

The dataset contains 8,091 images and 40,455 human-written captions, with five captions per image.

The project includes exploratory data analysis, text and image feature extraction, multimodal similarity analysis, image-caption matching, and neural image caption generation.

## Implemented Models

### 1. Multimodal Similarity Analysis

- Text representations using TF-IDF with unigram and bigram features.
- Dimensionality reduction using TruncatedSVD.
- Visual feature extraction using pretrained ResNet50 and PCA.
- Cosine similarity analysis between captions and between images.
- Comparison of visual and textual nearest neighbors.

### 2. Image-Caption Matching

- Binary classification of matching and non-matching image-caption pairs.
- Combination of visual and textual features.
- Logistic Regression classifier.
- Test F1-score: 0.7533.
- Test ROC-AUC: 0.7766.

### 3. Neural Image Caption Generation

- CNN-RNN encoder-decoder architecture.
- Pretrained ResNet50 as the image feature encoder.
- GRU-based recurrent language decoder.
- Vocabulary construction, tokenization, and sequence encoding.
- Cross-entropy loss and early stopping.
- Evaluation using BLEU and ROUGE metrics.
- Test BLEU-1: 0.5764.
- Test BLEU-4: 0.1634.
- Test ROUGE-L: 0.4514.

## Relevance to Neural Networks for NLP

The project covers several NLP-related concepts:

- Caption analysis, word frequencies, and rare-word distributions.
- Text preprocessing and vocabulary construction.
- TF-IDF, n-gram features, and text similarity.
- Multimodal text-image representations and matching.
- Neural sequence modeling and natural language generation using a GRU decoder.
- Evaluation of generated language using BLEU and ROUGE.

The most directly relevant component is the neural image caption generation model in Section 7 of the report.

### NLP-Related Report Sections

| Report Section | Pages | Main Topics |
| --- | --- | --- |
| 3.2–3.3 | 6–8 | Caption statistics, word frequencies, and vocabulary |
| 4.1 and 4.3 | 11–12 | Text preprocessing, TF-IDF, n-grams, and TruncatedSVD |
| 5 | 13–15 | Multimodal similarity and text-image alignment |
| 6 | 16–18 | Image-caption matching and classification |
| 7 | 19–23 | Neural caption generation, GRU decoder, training, and evaluation |

## Dataset

This project uses the Flickr8k dataset.

Dataset source:
https://www.kaggle.com/datasets/adityajn105/flickr8k

The dataset is not redistributed in this repository. Users should obtain it from the dataset provider, subject to the applicable terms.

### Dataset Setup

1. Download the Flickr8k dataset from the link above.
2. Extract the downloaded files.
3. Create a folder named `dataset` in the project root.
4. Place the image files inside `dataset/Images/`.
5. Place the captions file at `dataset/captions.txt`.

Expected directory structure:

```text
Flickr8k-Multimodal-NLP/
├── dataset/
│   ├── Images/
│   └── captions.txt
├── notebooks/
│   └── 01_flickr8k_data_audit_eda.ipynb
├── report/
│   └── Project_Report_English.pdf
├── README.md
├── requirements.txt
└── .gitignore
```

## Running the Project

1. Download or clone this repository.
2. Download and arrange the Flickr8k dataset as described above.
3. Install the Python packages required by the notebook.
4. Open `notebooks/01_flickr8k_data_audit_eda.ipynb` in Jupyter Notebook.
5. Set the working directory to `notebooks`.
6. Run the notebook cells in order.

The notebook includes saved experimental outputs for reference.

Note: Reproducing the experiments requires a compatible Python environment and may require additional setup for model training and cached features.

## Project Report

The English report provides detailed explanations of the methodology, preprocessing, model architectures, experimental results, evaluation metrics, and limitations.

## Author

Hasti Homayooni

Computer Engineering / Computer Science
