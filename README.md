
# CSE422 Lab Project: Hotel Booking Cancellation Prediction

This repository contains the full implementation of the CSE422 Machine Learning project focused on predicting hotel booking cancellations using Supervised and Unsupervised Learning techniques, including Deep Learning (ANN).

---

## 📌 Table of Contents
1. [Overview](#overview)
2. [Dataset Description](#dataset-description)
3. [Project Workflow](#project-workflow)
4. [Models & Algorithms Used](#models--algorithms-used)
5. [Evaluation Metrics](#evaluation-metrics)
6. [Installation & Usage](#installation--usage)
7. [Results Summary](#results-summary)

---

## 📖 Overview
The aim of this project is to analyze guest booking behavior and accurately predict whether a reservation will be canceled. By accurately predicting cancellations, hotel administrators can optimize revenue management, re-allocate rooms efficiently, and reduce loss due to empty rooms.

---

## 📊 Dataset Description
The dataset contains hotel reservation details, including booking leads, length of stay, demographic attributes, and previous cancellation history.

* **Target Variable:** `is_canceled` (0 = Not Canceled, 1 = Canceled)
* **Key Features:**
  * `lead_time`, `arrival_date_year`, `arrival_date_month`
  * `stays_in_weekend_nights`, `stays_in_week_nights`
  * `adults`, `children`, `babies`
  * `meal`, `market_segment`, `distribution_channel`
  * `deposit_type`, `customer_type`, `adr` (Average Daily Rate)

---

## ⚙️ Project Workflow

1. **Data Preprocessing & Cleaning:**
   * Handled missing values (e.g., imputed missing values in `children`).
   * Removed features causing data leakage (`reservation_status`, `reservation_status_date`).
   * Dropped high-cardinality and high-null columns (`company`, `agent`, `country`).
2. **Feature Engineering & Selection:**
   * One-Hot Encoding for categorical values.
   * Applied `VarianceThreshold` to remove quasi-constant features.
   * Scaled numerical features using `StandardScaler`.
3. **Model Training:**
   * Train-Test split (80% Train, 20% Test) with stratification.
   * Model implementations with hyperparameter configurations.
4. **Clustering:**
   * Applied **K-Means Clustering** ($k=2$) to explore underlying group structure.
5. **Evaluation & Visualization:**
   * Evaluated metrics (Accuracy, Precision, Recall, F1-Score).
   * Plotted Confusion Matrices and ROC-AUC curves.

---

## 🤖 Models & Algorithms Used

* **Supervised Machine Learning:**
  * **Logistic Regression** (Baseline model)
  * **Decision Tree Classifier**
  * **K-Nearest Neighbors (KNN)**
* **Deep Learning:**
  * **Artificial Neural Network (ANN)** built with TensorFlow/Keras (Dense layers with Dropout regularization)
* **Unsupervised Machine Learning:**
  * **K-Means Clustering**

---

## 📈 Evaluation Metrics

The performance of each model is measured using:
* **Accuracy:** Overall correctness of predictions.
* **Precision:** Accuracy of positive cancellation predictions.
* **Recall:** Ability to capture actual cancellations.
* **F1-Score:** Harmonic mean of Precision and Recall (Primary decision metric).
* **ROC-AUC Curve:** Evaluates true positive vs. false positive tradeoffs.

---

## 🚀 Installation & Usage

### Prerequisites
Make sure you have Python 3.8+ and the following libraries installed:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow
```

### Running the Notebook / Code
1. Clone the repository:
   ```bash
   git clone https://github.com/YourUsername/YourRepoName.git
   cd YourRepoName
   ```
2. Ensure the dataset `hotel_bookings.csv` is in the same directory.
3. Run the script or open the Jupyter Notebook:
   ```bash
   jupyter notebook CSE422_Lab_Project.ipynb
   ```

---

## 🏆 Results Summary

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| Logistic Regression | ~0.79 | ~0.76 | ~0.61 | ~0.68 |
| Decision Tree | ~0.84 | ~0.81 | ~0.75 | ~0.78 |
| KNN | ~0.82 | ~0.78 | ~0.71 | ~0.74 |
| Artificial Neural Network (ANN) | ~0.85 | ~0.82 | ~0.76 | ~0.79 |

*(Note: Replace approximate values above with your exact final evaluation results from the executed code).*
