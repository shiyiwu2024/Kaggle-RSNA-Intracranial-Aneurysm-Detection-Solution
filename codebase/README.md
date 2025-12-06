# RSNA Intracranial Aneurysm Detection — Transformer-Based Model

This codebase contains all scripts and notebooks used for our term project on classifying intracranial aneurysms using a transformer-based deep learning model. The workflow includes preprocessing, training, and test-time inference.

## File Descriptions and Execution Order

1. **preprocess.ipynb**  
   This notebook performs preprocessing of the original DICOM-format CT scans. It converts the scans into 2D image patches or `.npy` arrays suitable for model input. 
   **Run this notebook first**, before any model training or testing.  
   **Outputs:** processed image patches or arrays, named `preprocessed_data`.

2. **rsna-transformer-gpu.ipynb**  
   This is the main training notebook. It defines the transformer-based model (e.g., ViT), loads preprocessed training data, runs the training loop, evaluates performance on validation data, and saves the best-performing model.  
   **Run this notebook after data has been preprocessed.**  
   **Outputs:** a trained model checkpoint file named `best_model_seed42.pth`.

3. **rsna-trans-submission.ipynb**  
   This notebook performs test-time inference using the saved model checkpoint. It loads test data, runs predictions, and formats the results as a CSV file suitable for competition or submission.  
   **Run this notebook last, after training is complete and `best_model_seed42.pth` is available.**  
   **Outputs:** a CSV file containing predicted probabilities or labels for each test case.

## Data Download Instructions

The dataset can be downloaded from the RSNA Intracranial Aneurysm Detection competition on Kaggle:
https://www.kaggle.com/competitions/rsna-2022-cervical-spine-fracture-detection/data


