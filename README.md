# Robust-Food-Classification

## Introduction
In this project, we developed a robust food image classification system at the University of Milan-Bicocca. We worked with a challenging dataset comprising 251 food categories, with 20 images per class, facing several inherent difficulties including varying image dimensions, incorrect labels, and images that didn't precisely match their assigned categories. We explored various approaches to improve classification accuracy, starting with feature extraction methods using pre-trained models like MobileNetV2, implementing custom CNNs, and eventually moving to more sophisticated techniques including data cleaning, dataset augmentation, and model fine-tuning. Through systematic experimentation and iteration, we worked to overcome the limitations of the small dataset size and improve our model's ability to accurately classify food images across a diverse range of categories. The results were then applied to a degraded test set and more work was done to attempt improving the performance on it.

## How to Use

### Setting Up the Environment
1. **Google Colab**: Open the provided notebook in Google Colab. You can place the notebook in any directory within your Colab environment.

2. **Dataset**: 
   - Download the datasets zip files (and all the extensions), extract them and re-zip them individually with the same names (visual_train_set.zip, visual_val_set.zip, ...), and upload them to the root folder of your Google Drive (`myDrive`). The compressed folders had to be divided to avoid GitHub's 100MB maximum file size. Place the csv files in the same root directory.
   - Do not rename the dataset's zip files.

3. **Pre-Computed Models and Results**:
   - If you want to use pre-computed models and results (suggested), download the "RFCP Models" folder and place it in the root folder of your Google Drive (`myDrive`).
   - This folder contains trained models and results that can be directly used for inference or further analysis.
