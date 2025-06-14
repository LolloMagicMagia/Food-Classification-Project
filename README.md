# Robust Food Classification

**Visual Information Processing and Management – University of Milano-Bicocca**  
**Academic Year:** 2024–2025  
**Final Grade:** 30 cum laude  
**Authors:** Matteo Breganni (869549), Lorenzo Monti (869960)

---

## 🧠 About the Project

This project focuses on developing a **robust image classification system** for food categories, using a dataset composed of:

- **251 food classes**
- **~20 images per class**
- Images of varying quality, size, and labeling accuracy

We tackled the **challenges of data scarcity and inconsistency** through a combination of:
- Feature extraction (MobileNetV2)
- Custom CNNs
- Transfer learning and fine-tuning (MobileNetV2, DenseNet121)
- Data cleaning and outlier detection
- Dataset augmentation
- Advanced evaluation on **degraded test sets**

---

## 📁 Project Structure

- **Notebooks**: All exploratory work and experiments are in Colab notebooks
- **Models**: Trained models are stored as serialized `.h5` or `.pt` files (available in the "RFCP Models" folder)
- **Datasets**: Divided zip archives to fit GitHub size limits (uploaded manually to Google Drive)
- **Precomputed Results**: Optional for direct inference or further analysis

---

## ⚙️ How to Use

### 1. Google Colab Setup
- Open the provided notebook in Google Colab.
- Mount your Google Drive and place the zip datasets in the root of `/myDrive`.

### 2. Dataset Setup
- Datasets must retain the following names:
  - `visual_train_set.zip`, `visual_val_set.zip`, etc.
- Extract, re-zip individually, and upload all parts as-is.
- Include all associated `.csv` files in the same root folder.

### 3. Precomputed Models (Optional)
- Download the folder `RFCP Models` and place it in `/myDrive`.
- This folder includes:
  - Trained model checkpoints
  - Outlier sets
  - Evaluation metrics and logs

---

## 🔍 Methodology Highlights

### 🧪 Initial Approaches
- Feature extraction with **MobileNetV2** + SVM/KNN
- Custom CNN from scratch (Top-1 Accuracy: ~1.6%)
- Fine-tuned **MobileNetV2** and **DenseNet121** (Top-1: ~26%, Top-5: ~53%)

### 🧼 Dataset Cleaning
Used multiple outlier detection algorithms:
- K-Means, DBSCAN, Isolation Forest, Nearest Neighbors, OneClassSVM, KD-Tree
- Developed a **weighted consensus method** based on scoring precision
- Validated impact of removing "dirty" images using custom metrics

Result:
- Small improvements in accuracy when removing ~91 images
- Best test accuracy after cleaning and tuning: **~28%**

### 🔁 Data Augmentation
Applied augmentations to the cleaned dataset:
- **Translation**, **Brightness**, **Rotation**, **Contrast**
- Brightness gave the best performance boost (up to ~26% Top-1)

---

## 🧪 Advanced Fine-Tuning

### 📦 Final Model Improvements
- Used **unfrozen DenseNet121** for further fine-tuning
- Introduced **class-weighted loss** to account for imbalance after cleaning

Final results on clean test set:
- **Test Accuracy (Top-1): ~34%**
- **Top-5 Accuracy: ~61%**

---

## 🧪 Test Set Degradation

Simulated real-world noisy data:
- Applied **Gaussian noise**, **JPEG compression**, **Blur**
- Tested performance degradation

On degraded validation set:
- **Accuracy drop to ~23%**
- **Top-5 Accuracy drop to ~45%**

Trained on **mixed dataset** (clean + artificially degraded):
- Improved robustness
- **Accuracy on degraded set: ~24% (+4%)**
- **Top-5 Accuracy: ~48% (+7%)**

---

## 📊 Results Summary

| Dataset Type     | Top-1 Accuracy | Top-5 Accuracy | Test Loss |
|------------------|----------------|----------------|-----------|
| Clean (initial)  | ~26%           | ~53%           | ~3.28     |
| Clean (final)    | **~34%**       | **~61%**       | ~2.93     |
| Degraded         | ~23%           | ~45%           | ~3.92     |
| Mixed (train)    | ~24%           | ~48%           | ~3.56     |

---

## 🧪 Outlier Detection Algorithms Used

- `Nearest Neighbors`  
- `OneClass SVM`  
- `K-Means Clustering`  
- `DBSCAN`  
- `KD-Tree`  
- `Isolation Forest`

Consensus weighting was used to identify most likely "dirty" samples.

---

## 📈 Tools & Frameworks

- **Python 3.10+**
- **TensorFlow / Keras**
- **PyTorch (for optional models)**
- [**OpenCV**](https://learnopencv.com/)  
- [**BRISQUE**](https://learnopencv.com/image-quality-assessment-brisque/)  
- **Google Colab**

---

## 📌 Key Takeaways

- A small, noisy dataset requires **strong preprocessing** to be usable.
- **Ensemble outlier detection + consensus** helped improve data quality.
- Best classification results reached **~34% Top-1** and **~61% Top-5** on clean data.
- Robustness was improved using **mixed (degraded + clean)** training.
- Automatic degradation identification (BRISQUE, Laplacian filters) shows promise for future work.

---

## 🎓 Acknowledgements

This project was carried out as part of the *Visual Information Processing and Management* course at the **University of Milano-Bicocca**, under the guidance of the teaching staff in the 2024–2025 academic year.

---

## 📎 Related Materials

- 📑 [Download the project presentation (PDF)](https://github.com/LolloMagicMagia/Food-Classification-Project/blob/main/Presentazione.pdf)  

---

> “Training robust classifiers is not only about designing good models — it's about understanding your data.”  
> — *Project Team, 2024*
