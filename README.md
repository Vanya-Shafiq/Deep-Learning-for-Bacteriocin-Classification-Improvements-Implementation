# Deep-Learning-for-Bacteriocin-Classification-BacLABNet  
## Base Paper Reproduction + Improvements

This repository contains two complete implementations:

1. **Base Paper Implementation** — Reproduction of the original BacLABNet deep learning workflow.
2. **Improved Model** — My enhanced version using modern ML techniques for better accuracy and robustness.

---

## Project Summary

The goal is to classify protein sequences into:

- **BacLAB (1)** — bacteriocins produced by Lactic Acid Bacteria  
- **Non-BacLAB (0)** — bacteriocins from other organisms  

The base model follows the original research design, while the improved model adds more powerful techniques to enhance performance.

---

## Base Paper Implementation

The reproduction includes:

- k-mer extraction (3, 5, 7, 15, 20)
- Top 100 frequent k-mers → binary feature vectors
- Pretrained GRU embedding model (128-D)
- Concatenated features passed into a Deep Neural Network
- 30-fold cross-validation
- Metrics: Accuracy, Loss, Precision, Recall, F1

**Best base model performance:**  
Accuracy: **91.47%** with 5-mer + 7-mer + embedding vector combo.

---

## Improvements Added

The improved notebook includes four major enhancements:

### 1. Train-Only TF-IDF k-mer Extraction  
Prevents data leakage, improves generalization.

### 2. Mixup Data Augmentation  
Smooths decision boundaries & reduces overfitting.

### 3. Class-Balanced Focal Loss  
Handles class imbalance and focuses training on hard samples.

### 4. Ensemble Neural Networks  
Averages multiple DNN outputs for higher stability and accuracy.

---

## Dataset

Used sequences from UniProt with:

- Length: 50–2000 amino acids
- ~25k BacLAB sequences
- ~25k Non-BacLAB sequences  

---

## Reference (Base Paper)
González LL et al. (2025).  
*Deep learning neural network development for the classification of bacteriocin sequences produced by lactic acid bacteria.*

---

## License
Open for academic and research use.

