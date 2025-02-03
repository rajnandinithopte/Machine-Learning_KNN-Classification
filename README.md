# Machine Learning: KNN Classification on Vertebral Column Data

## 🔷 Overview
This project applies **K-Nearest Neighbors (KNN) classification** to the **Vertebral Column Data Set**, a biomedical dataset that categorizes spinal conditions into **normal** and **abnormal** classes. The implementation involves **data preprocessing, exploratory analysis, model training, evaluation, and experimentation** with different distance metrics and voting methods.

---

## 🔷 Dataset Description
The **Vertebral Column Data Set** is obtained from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Vertebral+Column). It consists of **310 samples** with **6 biomechanical attributes** extracted from radiographic images of the spine.

### 🔶 Features in the Dataset
- Pelvic incidence
- Pelvic tilt
- Lumbar lordosis angle
- Sacral slope
- Pelvic radius
- Grade of spondylolisthesis

Each row represents a **patient's spinal measurements**, and the **target variable** classifies the patient as:
- **Normal (0)**
- **Abnormal (1)** (includes conditions like herniated discs and spondylolisthesis)

---

## 🔷 Libraries Used
To execute this project, the following Python libraries were used:

- **pandas** → Data manipulation and preprocessing
- **numpy** → Numerical computations
- **matplotlib** → Data visualization
- **seaborn** → Statistical data visualization
- **scikit-learn** → Machine learning algorithms (KNN classifier, distance metrics, model evaluation)

## 🔷 Steps Taken to Accomplish the Project

### 🔶 1. Data Preprocessing and Exploratory Data Analysis (EDA)
- Converted categorical class labels into binary labels (Normal=0, Abnormal=1).
- Conducted scatterplot analysis to visualize relationships between independent variables.
- Created boxplots to identify outliers and distribution differences across the two classes.
- Split the dataset into training (first 70 rows of Class 0 and first 140 rows of Class 1) and test sets (remaining data).

### 🔶 2. K-Nearest Neighbors (KNN) Classification
- Implemented KNN with Euclidean distance using either a custom algorithm or scikit-learn’s implementation.
- Evaluated test errors for different values of k within `{208, 205, ..., 7, 4, 1}`.
- Selected the optimal k by plotting training and test errors vs. k.
- Computed performance metrics for the optimal k:
  - Confusion Matrix
  - True Positive Rate (Recall)
  - True Negative Rate
  - Precision
  - F1-Score

### 🔶 3. Learning Curve Analysis
- Investigated the effect of training size on KNN performance.
- Trained the model using different training set sizes `N = {10, 20, 30, …, 210}`.
- Selected the optimal k dynamically for each training size.
- Plotted the learning curve (test error vs. training set size) to analyze model generalization.

### 🔶 4. Experimentation with Different Distance Metrics
- Replaced Euclidean distance with alternative distance measures:
  - Minkowski Distance `(p = 1 → Manhattan, log₁₀(p) ∈ {0.1, 0.2, …, 1}, p → ∞ → Chebyshev)`
  - Mahalanobis Distance (accounting for feature correlations)
- Compared test errors across distance metrics and summarized results in a table.

### 🔶 5. Weighted Voting in KNN
- Implemented distance-weighted voting, where closer neighbors contribute more to the decision.
- Compared performance with Euclidean, Manhattan, and Chebyshev distances.
- Identified the best test error with `k ∈ {1, 6, 11, …, 196}`.

### 🔶 6. Final Evaluation
- Reported lowest training error achieved across all experiments.
- Summarized findings on the best k-value, distance metric, and voting method.
