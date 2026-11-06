
# Flickr8k Multimodal NLP Project

## Overview

This project explores multimodal learning by combining **Natural Language Processing (NLP)** and **Computer Vision** using the Flickr8k dataset.

The dataset contains **8,091 images and 40,455 human-written captions**, with five captions per image.

The project includes exploratory data analysis, text and image feature extraction, multimodal similarity analysis, image-caption matching, and neural image caption generation.

## Implemented Models

### 1. Multimodal Similarity Analysis

- Text representations using TF-IDF with unigram and bigram features.
- Dimensionality reduction using TruncatedSVD.
- Visual feature extraction using pretrained ResNet50 and PCA.
- Cosine similarity analysis between captions and between images.
- Comparison of visual and textual nearest neighbors.
- Average visual-textual top-5 neighbor overlap: **0.3103**.

### 2. Image-Caption Matching

- Binary classification of matching and non-matching image-caption pairs.
- Combination of visual and textual features.
- Logistic Regression classifier.
- Validation-based threshold selection.

**Test Results:**

| Metric | Score |
| --- | ---: |
| Accuracy | 0.6998 |
| Precision | 0.6393 |
| Recall | 0.9168 |
| F1-score | 0.7533 |
| ROC-AUC | 0.7766 |

### 3. Neural Image Caption Generation

A CNN-RNN encoder-decoder architecture for generating natural-language descriptions of images.

- Pretrained ResNet50 as the image encoder.
- GRU-based recurrent language decoder.
- Vocabulary construction, tokenization, and numerical encoding.
- Sequence modeling with padding and special tokens.
- Cross-entropy loss and early stopping.
- Evaluation using BLEU and ROUGE metrics.

**Test Results:**

| Metric | Score |
| --- | ---: |
| BLEU-1 | 0.5764 |
| BLEU-2 | 0.3889 |
| BLEU-3 | 0.2456 |
| BLEU-4 | 0.1634 |
| ROUGE-L | 0.4514 |

The best caption-generation model was selected at epoch 9 based on validation performance.

## Relevance to Neural Networks for NLP

This project covers several concepts related to Natural Language Processing:

- Caption analysis, word frequencies, and rare-word distributions.
- Text preprocessing, tokenization, and vocabulary construction.
- TF-IDF, n-gram representations, and textual similarity.
- Multimodal text-image matching.
- Neural sequence modeling using recurrent networks.
- Natural language generation with a GRU decoder.
- Evaluation of generated text using BLEU and ROUGE.

The most directly relevant component is **Model 3: Neural Image Caption Generation**, which applies neural sequence modeling to generate captions conditioned on image features.

### NLP-Related Report Sections

| Report Section | Pages | Main Topics |
| --- | --- | --- |
| 3.2–3.3 | 6–8 | Caption statistics, word frequencies, and vocabulary |
| 4.1 and 4.3 | 11–12 | Text preprocessing, TF-IDF, n-grams, and TruncatedSVD |
| 5 | 13–15 | Text similarity and multimodal alignment |
| 6 | 16–18 | Image-caption matching and classification |
| 7 | 19–23 | Neural caption generation, GRU decoder, training, and evaluation |

## Repository Contents

- **[Jupyter Notebook](notebooks/01_flickr8k_data_audit_eda.ipynb)** — Complete implementation of the three approaches, including saved experimental outputs.
- **[Project Report](report/Flickr8k_Project_Report.pdf)** — English report covering methodology, experiments, visualizations, results, and limitations.
- **[requirements.txt](requirements.txt)** — Python dependencies.
- **[.gitignore](.gitignore)** — Excludes the dataset, generated files, and local environment files.

## Dataset

This project uses the **Flickr8k dataset**.

**Dataset source:** [Flickr8k on Kaggle](https://www.kaggle.com/datasets/adityajn105/flickr8k)

The dataset is not redistributed in this repository. Users should obtain it from the dataset provider, subject to the applicable terms of use.

### Dataset Setup

1. Download the Flickr8k dataset from the link above.
2. Extract the downloaded files.
3. Create a folder named `dataset` in the project root.
4. Place the image files inside `dataset/Images/`.
5. Place the captions file at `dataset/captions.txt`.

The directory and file names should match the paths expected by the notebook.

### Expected Directory Structure

```text
Flickr8k-Multimodal-NLP/
├── dataset/
│   ├── Images/
│   └── captions.txt
├── notebooks/
│   └── 01_flickr8k_data_audit_eda.ipynb
├── report/
│   └── Flickr8k_Project_Report.pdf
├── README.md
├── requirements.txt
└── .gitignore
```

The `dataset` directory is created locally by the user and is excluded from the Git repository.

## Installation and Running the Project

### 1. Clone the Repository

```bash
git clone https://github.com/HastiHomayooni/Flickr8k-Multimodal-NLP.git
cd Flickr8k-Multimodal-NLP
```

Alternatively, download the repository as a ZIP file from GitHub.

### 2. Set Up the Python Environment

A compatible Python environment is required. Python 3.12 is recommended, although the full dependency combination has not been independently validated across operating systems.

For Windows, with Python 3.12 installed:

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install Dependencies

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

PyTorch installation may require platform-specific configuration for CUDA GPU support.

### 4. Prepare the Dataset

Download and organize Flickr8k as described in the **Dataset Setup** section.

### 5. Launch Jupyter Notebook

From the project root:

```bash
cd notebooks
python -m notebook
```

Open `01_flickr8k_data_audit_eda.ipynb`.

The notebook expects the current working directory to be `notebooks`, with the `dataset` directory located one level above it.

### 6. Run the Notebook

Execute the notebook cells in order to perform dataset analysis, feature extraction, model training, and evaluation.

The notebook contains saved experimental outputs for reference, so readers can inspect previously generated results without immediately rerunning the entire pipeline.

**Note:** Full execution may take considerable time because it includes ResNet50 feature extraction and GRU model training.

## Generated Files

During execution, the notebook creates the following directories:

```text
cache/
outputs/
├── figures/
└── tables/
```

- `cache/` stores extracted features, preprocessing artifacts, and saved models.
- `outputs/figures/` stores plots and visualizations.
- `outputs/tables/` stores analysis results and evaluation tables.

These generated directories are excluded from version control and can be recreated by running the notebook.

## Limitations and Future Work

The project has several limitations:

- Dependence on pretrained visual features.
- Limited coverage of rare words.
- Potential generation of frequent or generic captions.
- No attention mechanism in the GRU caption-generation architecture.
- Sensitivity to the available training data and model configuration.

Possible future improvements include attention mechanisms, Transformer-based caption decoders, and stronger visual-language alignment.

## Project Report

The **[English Project Report](report/Flickr8k_Project_Report.pdf)** provides detailed explanations of the dataset, preprocessing, model architectures, experiments, evaluation, qualitative examples, limitations, and conclusions.

## Author

**Hasti Homayooni**

Computer Engineering / Computer Science

---

*An academic project exploring Natural Language Processing, Computer Vision, and Multimodal Learning.*
