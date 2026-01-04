# CrackForest-Segmentation
# Pavement Crack Segmentation with U-Net

This project focuses on pavement crack segmentation using deep learning methods. 
A U-Net based model is trained and evaluated on the CrackForest dataset to perform binary crack segmentation.

The goal of this project is to automatically detect crack regions in road images and visualize the segmentation results.

---

## Dataset

The CrackForest dataset is used in this project. It contains pavement images and corresponding crack annotations.

- Images are RGB pavement photos.
- Ground truth labels are provided as segmentation masks.
- Crack pixels occupy only a small portion of each image, resulting in strong class imbalance.

During preprocessing, the original ground truth annotations were converted into binary masks for training.

---

## Method

A standard U-Net architecture is adopted for crack segmentation.

- Encoder-decoder structure with skip connections
- Binary segmentation output
- Loss function: Binary Cross Entropy with positive class weighting and Dice loss
- Data augmentation is applied to improve generalization

---

## Training

The model was trained using PyTorch with the following settings:

- Optimizer: AdamW
- Batch size: 6
- Number of epochs: 20
- Training device: GPU (Kaggle)

Due to frequent disconnections on Google Colab, all training was conducted on Kaggle.

---

## Results

The trained model is able to detect most major crack structures and align well with ground truth masks.
Some thin or low-contrast cracks are partially missed, which is expected given the challenging nature of the task.

The best validation performance achieved:

- IoU ≈ 0.34
- Dice ≈ 0.50

Several qualitative results are provided in the folder.

---

## Pretrained Model

The pretrained model weight is provided:

