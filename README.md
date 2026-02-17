# NeuroVision: Dual-Stage Deep Learning Framework for Brain Tumor Detection and Classification

## Abstract

NeuroVision presents a dual-stage deep learning pipeline for automated brain tumor detection and classification using MRI images. The framework separates tumor detection from tumor type classification to improve modularity, robustness, and interpretability.

---

## Methodology

### Stage 1: Binary Classification (Tumor vs No Tumor)
- Backbone: MobileNetV2 (ImageNet pretrained)
- Frozen convolutional base
- Custom dense classification head
- Binary cross-entropy loss

### Stage 2: Multi-Class Classification (Glioma, Meningioma, Pituitary)
- Backbone: EfficientNetB0 (ImageNet pretrained)
- Frozen feature extractor
- Fully connected classification layers
- Categorical cross-entropy loss

The two-stage design mimics a practical diagnostic workflow where detection precedes classification.

---

## Dataset

MRI brain images categorized into:
- Glioma
- Meningioma
- Pituitary
- No Tumor

The dataset is programmatically structured into:
- Training set
- Validation set
- Test set

Separate directory structures are generated for binary and multi-class training.

---

## Experimental Setup

- Input resolution: 224 × 224
- Optimizer: Adam
- Early stopping enabled
- Model checkpointing enabled
- Transfer learning with frozen convolutional backbones
- Data augmentation applied during training

---

## Evaluation

Model performance is evaluated using:
- Test accuracy
- Confusion matrices
- Classification reports

Grad-CAM visualization is implemented to improve interpretability by highlighting discriminative regions in MRI scans.

---

## Reproducibility

Running the notebook performs the following:

1. Dataset preprocessing and structuring  
2. Stage-1 model training (binary detection)  
3. Stage-2 model training (multi-class classification)  
4. Evaluation on test data  
5. Grad-CAM visualization for interpretability  

---

## Future Work

- Fine-tuning deeper convolutional layers
- Hyperparameter optimization
- Cross-validation for robustness analysis
- Lightweight deployment for clinical inference environments
