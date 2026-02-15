# Zero-Shot EEG Decoding via Cross-Modal Alignment

Research project exploring cross-modal alignment between EEG signals and pretrained visual and semantic embedding spaces for zero-shot classification.

---

## Overview

Traditional EEG classifiers rely heavily on labelled neural data and struggle to generalise to unseen categories.  
This project proposes a zero-shot decoding framework that maps EEG representations directly into structured embedding spaces.

Classification is performed using cosine similarity against class prototypes, enabling decoding of categories absent from training.

---

## Methodology

- EEG feature extraction (561-dimensional feature vectors)
- Dimensionality reduction of image embeddings (PCA → 100D)
- Transformer-based text embeddings (512D)
- Ridge regression baseline
- Dual-headed MLP for multimodal alignment
- Contrastive learning using InfoNCE loss
- Prototype-based classification via cosine similarity

---

## Model Design

### Baseline
Ridge regression provides a strong linear projection baseline due to the smooth geometry of embedding spaces.

### Nonlinear Model
A shallow MLP with a 256-unit hidden layer and dual output heads predicts:

- Image embeddings
- Text embeddings

Each output is L2-normalised to ensure compatibility with cosine similarity scoring.

Training uses InfoNCE contrastive loss to preserve relational similarity structure rather than absolute reconstruction.

---

## Key Results

- Ridge achieves strong unseen-category baseline performance
- Contrastive MLP improves seen-class alignment
- Late multimodal fusion achieves highest overall accuracy
- Image-based alignment outperforms text-based alignment in early EEG window (70–300 ms)

---

## Technical Stack

- Python
- NumPy
- Scikit-learn (Ridge regression)
- PCA (dimensionality reduction)
- Contrastive learning (InfoNCE)
- Cosine similarity-based prototype scoring

---

## Research Contributions

- Zero-shot neural decoding framework
- Cross-modal EEG-to-embedding alignment
- Comparative study of regression vs contrastive learning
- Multimodal late-fusion strategy
- Geometric analysis of decoding errors

---

## Future Work

- Temporal transformer-based modelling
- Subject-independent alignment
- Richer multimodal embedding architectures (e.g., CLIP-based models)
- Improved generalisation across unseen categories

---

## Author

Bejna Arslan  
MEng Computer Science – Durham University
