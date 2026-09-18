# YuvaIntern Week 1 — Python for ML & Data Preprocessing

A practical data preprocessing project completed as part of the **AI Pioneers Internship (Machine Learning Internship) at YuvaIntern**.

The project demonstrates how raw tabular data can be inspected, cleaned, transformed, visualized, and prepared for further machine learning workflows using Python and popular data science libraries.

---

## 📌 Project Overview

Data preprocessing is a critical step in a machine learning workflow. Real-world datasets commonly contain missing values, duplicate records, inconsistent categorical values, and numerical features with different scales.

In this project, an employee dataset was created for educational purposes and intentionally contains data-quality issues. A complete preprocessing workflow was implemented to transform the raw dataset into a cleaner, structured, and analysis-ready dataset.

### Key preprocessing tasks

* Data loading and inspection
* Data type and structure analysis
* Missing-value detection and handling
* Duplicate record detection and removal
* Categorical data cleaning
* Outlier detection and treatment using the IQR method
* Feature preparation
* Categorical variable encoding
* Numerical feature normalization
* Exploratory data analysis (EDA)
* Exporting processed data

---

## 🎯 Objectives

The main objectives of this project are to:

1. Load and inspect a tabular dataset using Pandas.
2. Identify missing values and duplicate records.
3. Clean inconsistent categorical values.
4. Handle missing numerical values using an appropriate imputation method.
5. Detect and treat potential numerical outliers.
6. Prepare relevant features for analysis.
7. Convert categorical variables into machine-readable numerical features.
8. Normalize numerical features.
9. Perform basic exploratory data analysis.
10. Export the processed dataset for future machine learning tasks.

---

## 🛠️ Technologies & Tools

| Technology           | Purpose                                  |
| -------------------- | ---------------------------------------- |
| **Python 3**         | Core programming language                |
| **Pandas**           | Data loading, cleaning, and manipulation |
| **NumPy**            | Numerical operations                     |
| **Matplotlib**       | Data visualization                       |
| **Seaborn**          | Statistical visualization                |
| **Scikit-learn**     | Machine learning preprocessing concepts  |
| **Jupyter Notebook** | Interactive development and analysis     |
| **VS Code**          | Development environment                  |
| **Git & GitHub**     | Version control and project hosting      |

---

## 📊 Dataset

The project uses a small sample **employee dataset** designed specifically for demonstrating data preprocessing techniques.

### Dataset characteristics

* **Raw records:** 13
* **Unique records after duplicate removal:** 11
* **Original features:** 7
* **Dataset type:** Tabular
* **Purpose:** Educational / Machine Learning preprocessing practice

### Features

| Feature            | Type        | Description                 | Preprocessing                               |
| ------------------ | ----------- | --------------------------- | ------------------------------------------- |
| `Age`              | Numerical   | Employee age                | Median imputation + normalization           |
| `Gender`           | Categorical | Gender category             | Text cleaning + encoding                    |
| `City`             | Categorical | Employee location           | Text cleaning + encoding                    |
| `Experience_Years` | Numerical   | Years of experience         | Median imputation + normalization           |
| `Monthly_Income`   | Numerical   | Monthly income              | IQR-based outlier treatment + normalization |
| `Education`        | Categorical | Education level             | Text cleaning + encoding                    |
| `Satisfaction`     | Numerical   | Employee satisfaction score | Normalization                               |

---

## 🔄 Preprocessing Workflow

The project follows the following workflow:

```text
Raw Dataset
     │
     ▼
Load Data
     │
     ▼
Initial Inspection
     │
     ├── Missing Values
     ├── Duplicate Records
     ├── Data Types
     └── Basic Statistics
     │
     ▼
Data Cleaning
     │
     ├── Remove Duplicates
     ├── Handle Missing Values
     └── Clean Categorical Text
     │
     ▼
Outlier Treatment
     │
     └── IQR-based Capping
     │
     ▼
Feature Preparation
     │
     ├── Categorical Encoding
     └── Numerical Normalization
     │
     ▼
EDA & Analysis
     │
     ▼
Processed Dataset
```

---

## 🔍 Techniques Implemented

### 1. Missing Value Handling

Missing numerical values were identified using Pandas and handled using **median imputation**.

Median was selected because it is relatively robust to extreme values and provides a simple baseline for small tabular datasets.

### 2. Duplicate Removal

Duplicate records were identified and removed to prevent repeated observations from affecting analysis.

```python
df = df.drop_duplicates()
```

### 3. Categorical Data Cleaning

Categorical text values were standardized using operations such as:

```python
.str.strip()
.str.title()
.str.upper()
```

This helps maintain consistent category labels before encoding.

### 4. Outlier Treatment

Potential outliers in `Monthly_Income` were detected using the **Interquartile Range (IQR)** method.

The detected extreme values were capped rather than removing complete records.

### 5. Categorical Encoding

Categorical variables such as:

* Gender
* City
* Education

were converted into numerical indicator columns using one-hot encoding.

### 6. Numerical Normalization

Min-Max normalization was applied to important numerical variables.

The transformation maps values approximately to the range:

```text
0 to 1
```

This can be useful for machine learning algorithms that are sensitive to feature scale.

---

## 📈 Exploratory Data Analysis

Basic EDA was performed to understand the cleaned dataset and identify useful patterns.

The project can include visualizations such as:

* Monthly income distribution
* Income boxplot
* Employee count by education
* Employee count by city
* Numerical feature relationships
* Correlation heatmap

These visualizations help understand distributions, category frequencies, relationships, and potential anomalies.

---

## 📁 Project Structure

```text
yuvaintern-week1-ml-preprocessing/
│
├── .gitignore
├── LICENSE
├── README.md
├── requirements.txt
│
├── data/
│   ├── raw/
│   │   └── dataset.csv
│   │
│   └── processed/
│
├── notebooks/
│   └── 1_Data_Preprocessing.ipynb
│
├── outputs/
│   ├── figures/
│   └── processed_data/
│
├── report/
│
└── src/
    └── preproocessing.py
```

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/GyanPrakash05/yuvaintern-week1-ml-preprocessing.git
```

**Meaning:** Downloads the GitHub repository to your computer.

### 2. Open the project directory

```bash
cd yuvaintern-week1-ml-preprocessing
```

**Meaning:** Moves the terminal into the project folder.

### 3. Create a virtual environment

```bash
python -m venv venv
```

**Meaning:** Creates an isolated Python environment for the project.

### 4. Activate the environment on Windows

```powershell
.\venv\Scripts\Activate.ps1
```

**Meaning:** Activates the project's virtual Python environment.

### 5. Install dependencies

```powershell
pip install -r requirements.txt
```

**Meaning:** Installs all Python packages listed in `requirements.txt`.

### 6. Launch Jupyter Notebook

```powershell
jupyter notebook
```

**Meaning:** Opens Jupyter Notebook so the preprocessing notebook can be executed interactively.

### 7. Run the notebook

Open:

```text
notebooks/1_Data_Preprocessing.ipynb
```

and execute the cells from top to bottom.

---

## 📦 Requirements

The main dependencies used in this project are:

```text
numpy
pandas
matplotlib
seaborn
scikit-learn
jupyter
ipykernel
```

Exact package versions are maintained in:

```text
requirements.txt
```

---

## 📌 Results

The preprocessing workflow transforms the raw employee dataset into a cleaner and more structured dataset suitable for further analysis and machine learning preparation.

Key outcomes include:

* Duplicate records removed
* Missing numerical values handled
* Categorical values standardized
* Potential income outliers treated
* Categorical variables encoded
* Numerical variables normalized
* Processed data prepared for future ML workflows

The processed dataset can be used as the starting point for subsequent machine learning tasks such as train-test splitting, feature engineering, model training, and evaluation.

---

## 🔮 Future Scope

This project can be extended by:

* Building reusable Scikit-learn preprocessing pipelines
* Performing deeper exploratory data analysis
* Applying advanced feature selection techniques
* Performing train-test splitting
* Implementing feature engineering
* Training supervised and unsupervised machine learning models
* Evaluating model performance
* Experiment tracking and reproducibility
* Developing a complete end-to-end ML pipeline

---

## 📚 Learning Outcomes

Through this project, the following practical concepts were reinforced:

* Working with Pandas DataFrames
* Understanding data quality issues
* Handling missing data
* Removing duplicate observations
* Cleaning categorical variables
* Understanding outliers and IQR
* Encoding categorical features
* Normalizing numerical data
* Performing basic EDA
* Organizing an ML project
* Using Git and GitHub for version control

---

## 👨‍💻 Author

**Gyan Prakash**

AI/ML Learner | Python | Data Science | Machine Learning

---

## 🎓 Internship

**AI Pioneers Internship — Machine Learning Internship**

**Organization:** YuvaIntern
**Task:** Week 1 — Python for Machine Learning & Data Preprocessing
**Date:** September 2026

---

## 📖 References

* YuvaIntern — AI Pioneers Internship
* Scikit-learn Documentation
* Pandas Documentation
* NumPy Documentation
* Matplotlib Documentation
* Seaborn Documentation

---

## 📄 Project Report

A detailed project report covering the preprocessing methodology, dataset description, results, observations, conclusion, and future scope is included in the `report/` directory.
