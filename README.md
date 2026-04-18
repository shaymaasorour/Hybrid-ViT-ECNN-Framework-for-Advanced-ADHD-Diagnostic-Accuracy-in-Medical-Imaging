# Hybrid-ViT-ECNN-Framework-for-Advanced-ADHD-Diagnostic-Accuracy-in-Medical-Imaging

This repository contains the implementation of a hybrid deep learning framework for ADHD classification from pediatric brain MRI. The proposed model combines a Vision Transformer (ViT) and an Enhanced Convolutional Neural Network (ECNN) within a biologically informed multi-stream preprocessing pipeline based on Raw MRI, Phase Spectrum Transform (PST), and Quantile Histogram Equalization with Denoising (QHED).

## Summary

The framework is designed to improve ADHD diagnostic classification by integrating complementary global and local feature learning. The ViT branch captures long-range structural relationships, whereas the ECNN branch extracts localized morphological patterns. These two representations are fused to generate the final prediction.

The study was conducted on the ADHD-200 Neuroimage Slices dataset and demonstrated that the hybrid ViT+ECNN model outperformed standalone ViT and ECNN baselines, achieving 99.4% accuracy, 99.3% precision, 99.5% recall, and an F1-score of 0.99.

## Key Features

- Hybrid ViT and ECNN architecture
- Multi-stream preprocessing using Raw, PST, and QHED inputs
- Comparative evaluation against standalone models
- Structural ablation analysis
- Hyperparameter sensitivity analysis
- Complexity and deployment efficiency analysis
- Explainability using attention rollout and Grad-CAM

## Dataset

The experiments were performed on the publicly available ADHD-200 Neuroimage Slices dataset.

Dataset link:


https://www.kaggle.com/datasets/shaymaasorour/adhd-200-neuroimage-slices
Preprocessing

Each MRI slice is processed through three complementary representations:

Raw MRI
PST
QHED

All images are resized to 224 × 224, transformed into tensors, and normalized before training.

Model

The proposed framework consists of:

ViT branch for global contextual representation
ECNN branch for local feature extraction from Raw, PST, and QHED streams
Fusion layer for integrating global and local features
Classifier for final ADHD/TDC prediction
Main Results
Hybrid ViT+ECNN performance
Accuracy: 99.4%
Precision: 99.3%
Recall: 99.5%
F1-score: 0.99
Structural ablation
ECNN only: 0.8880 accuracy
ViT only: 0.9280 accuracy
ViT+ECNN: 0.9597 accuracy

These results confirm that the hybrid design provides stronger diagnostic performance than either branch individually.

Model Complexity
Model	Parameters	FLOPs	Inference Time
ECNN	389,890	0.19 G	4.12 ms
ViT	85.8 M	16.86 G	18.63 ms
ViT+ECNN	86.19 M	17.05 G	23.41 ms
Repository Contents
.
├── ViT.ipynb
├── ECNN.ipynb
├── Combined.ipynb
├── Comments response.ipynb
├── Comments response v2.ipynb
├── README.md
├── requirements.txt
└── LICENSE
Installation
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
cd YOUR_REPOSITORY_NAME
pip install -r requirements.txt
Usage

Run the notebooks according to the model type:

ViT.ipynb for the Vision Transformer model
ECNN.ipynb for the Enhanced CNN model
Combined.ipynb for the hybrid ViT+ECNN framework

