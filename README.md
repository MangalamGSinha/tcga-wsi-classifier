# tcga-wsi-classifier
# TCGA Breast Cancer WSI Image Classifier

## Overview
This project is a deep learning-based classifier for whole-slide images (WSIs) of breast cancer from the TCGA dataset. The model is designed to distinguish between tumor and normal tissue slides using EfficientNet and patch-based analysis.

## Features
- **Whole-slide image classification**: Distinguishes between tumor and normal tissue.
- **Patch extraction**: Extracts patches from WSIs for deep learning processing.
- **EfficientNet-based model**: Utilizes EfficientNet for feature extraction and classification.
- **Dataset**: Uses diagnostic slides from the TCGA dataset.
- **Automated preprocessing**: Handles tissue segmentation and patch selection.

## Installation
### Prerequisites
Ensure you have the following installed:
- Python 3.8+
- TensorFlow / PyTorch
- OpenSlide
- NumPy, Pandas, Matplotlib
- Tqdm, Albumentations

### Setup
Clone the repository and install dependencies:
```bash
git clone https://github.com/your-username/tcga-wsi-classifier.git
cd tcga-wsi-classifier
pip install -r requirements.txt
```

## Usage
### 1. Extract Patches
Run the patch extraction script to generate smaller image patches from WSIs:
```bash
python extract_patches.py --input /path/to/svs/files --output /path/to/patches
```

### 2. Train the Classifier
Train the model using the extracted patches:
```bash
python efficient_net.py --train --data /path/to/patches --epochs 50
```

### 3. Evaluate the Model
Evaluate the model performance on the test set:
```bash
python efficient_net.py --evaluate --data /path/to/test/patches
```

### 4. Classify New WSIs
To classify new whole-slide images:
```bash
python efficient_net.py --predict --input /path/to/new/svs/files
```

## Directory Structure
```
📂 tcga-wsi-classifier
├── 📂 data                 # Raw WSI data
├── 📂 patches              # Extracted image patches
├── 📂 models               # Trained models
├── extract_patches.py      # Patch extraction script
├── efficient_net.py        # Classification model script
├── requirements.txt        # Dependencies
├── README.md               # Project documentation
```


## References
- [TCGA Dataset](https://portal.gdc.cancer.gov/)
- [EfficientNet](https://arxiv.org/abs/1905.11946)
- [OpenSlide](https://openslide.org/)


