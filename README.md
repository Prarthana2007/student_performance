# student_performance
# 🎓 Student Mathematics Performance Prediction
### Exploratory Data Analysis, Statistical Visualization & Deep Learning

<p align="center">
  <strong>Exploring student academic performance through data-driven insights and neural network classification.</strong>
</p>

---

## 📌 Project Overview

Student academic performance is influenced by several academic, demographic, family, and behavioural factors. Understanding these factors can help educational institutions investigate learning patterns and identify areas where additional academic support may be beneficial.

This project applies **Exploratory Data Analysis (EDA), statistical analysis, data visualization, and Deep Learning** to the Student Performance dataset from the UCI Machine Learning Repository.

The project explores Mathematics grade distributions, investigates relationships between study habits and academic outcomes, and develops a **Multi-Layer Perceptron (MLP) neural network** to classify students into pass and fail categories.

## 🎯 Objectives

- Analyze student Mathematics performance using a real-world dataset.
- Examine missing values, duplicate records, and potential outliers.
- Perform descriptive statistical analysis and distribution analysis.
- Explore relationships between academic, demographic, and behavioural attributes.
- Apply categorical encoding and numerical standardization.
- Build a Deep Learning model for binary pass/fail classification.
- Evaluate the model using classification metrics and visualizations.
- Interpret findings and identify opportunities for future improvement.

## 📂 Dataset

**Dataset:** Student Performance — Mathematics (`student-mat.csv`)

**Source:** UCI Machine Learning Repository

**Dataset link:** https://archive.ics.uci.edu/dataset/320/student+performance

| Property | Description |
|---|---|
| Original records | 395 students |
| Original attributes | 33 columns |
| File format | CSV |
| CSV delimiter | Semicolon (`;`) |
| Prediction task | Binary classification |
| Target variable | `Pass` |
| Passing criterion | Final Mathematics grade (`G3`) ≥ 10 |

### Feature Categories

- **Demographic:** Age, sex, address and family size.
- **Family background:** Parents' education, occupation and family support.
- **Academic:** Study time, previous grades and past failures.
- **Attendance and health:** Absences and health-related attributes.
- **Social and behavioural:** Free time, going out and weekday/weekend alcohol consumption.

The target variable `Pass` is derived from the final Mathematics grade (`G3`):

- `1` — Pass: G3 ≥ 10
- `0` — Fail: G3 < 10

The original `G3` column is excluded from model inputs to prevent target leakage. Earlier grades (`G1` and `G2`) are retained as predictors.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Google Colab | Cloud-based development environment |
| Pandas | Data loading, manipulation and analysis |
| NumPy | Numerical computation |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Preprocessing, data splitting and evaluation |
| TensorFlow / Keras | Deep Learning model development |

## 🔍 Exploratory Data Analysis

The project investigates the dataset through multiple analytical techniques.

### 1. Data Quality Analysis
- Dataset dimensions and data types.
- Missing-value analysis.
- Duplicate-record detection.
- Potential outlier identification using the Interquartile Range (IQR) method.

### 2. Statistical Analysis
- Mean, median and standard deviation.
- Minimum, maximum and quartiles.
- Distribution and skewness analysis.
- Correlation analysis between numerical attributes.

### 3. Data Preprocessing
- Removal of duplicate records where identified.
- Missing-value imputation where required.
- One-Hot Encoding of categorical features.
- Standardization of numerical features.
- Stratified training, validation and testing splits.

### 4. Data Visualization

| Visualization | Analytical Purpose |
|---|---|
| Pass/Fail Distribution | Examine class distribution |
| Final Grade Histogram with KDE | Understand grade distribution and skewness |
| Boxplot of Study Time vs Final Grade | Compare grades across study-time categories |
| Absences vs Final Grade Scatter Plot | Investigate attendance and grade patterns |
| Numerical Correlation Heatmap | Identify relationships among numerical features |

These visualizations help reveal patterns and associations in the dataset. They do not, by themselves, establish causation.

## 🧠 Deep Learning Model

A **Multi-Layer Perceptron (MLP)** is implemented using TensorFlow/Keras for binary classification.

### Model Workflow

1. Prepare the input features and binary target.
2. Split the data into training, validation and testing subsets.
3. Apply preprocessing fitted only on the training data.
4. Train the MLP using the training dataset.
5. Monitor validation performance during training.
6. Generate predictions on the held-out test dataset.
7. Evaluate classification performance using suitable metrics.

### Model Architecture

The neural network uses:
- An input layer corresponding to the preprocessed features.
- Fully connected Dense hidden layers.
- ReLU activation for hidden layers.
- Dropout regularization, where configured.
- A sigmoid output layer for pass/fail probability prediction.

### Training Configuration

| Parameter | Configuration |
|---|---|
| Model | Multi-Layer Perceptron |
| Framework | TensorFlow / Keras |
| Optimizer | Adam |
| Loss function | Binary Cross-Entropy |
| Output activation | Sigmoid |
| Random seed | 42 |
| Data split | 70% training, 15% validation, 15% testing |

The exact layer sizes, number of epochs, batch size and other hyperparameters are documented in the Colab notebook.

## 📊 Model Evaluation

Model performance is evaluated using the following methods:

- **Accuracy:** Overall proportion of correct predictions.
- **Confusion Matrix:** Distribution of true and incorrect classifications.
- **ROC Curve:** Trade-off between true-positive and false-positive rates.
- **ROC-AUC:** Ability of the model to distinguish between the two classes.
- **Training and Validation Curves:** Monitoring learning progress and potential overfitting.

### Results

| Metric | Result |
|---|---|
| Test Accuracy | Add actual Colab result |
| ROC-AUC | Add actual Colab result |
| Confusion Matrix | Include generated output |
| Training/Validation Curves | Include generated plots |

*All reported values should be taken from the final executed notebook.*

## 📈 Key Findings

The analysis is designed to investigate:

- The distribution of final Mathematics grades.
- Differences in grades across study-time categories.
- Patterns between student absences and final grades.
- Relationships among previous grades and other numerical attributes.
- The effectiveness of an MLP model for pass/fail classification.

Final conclusions should be updated according to the actual EDA outputs and test results obtained during execution.

## 🚀 How to Run the Project

### Option 1: Google Colab (Recommended)

1. Download or clone this repository.
2. Open the `.ipynb` notebook in Google Colab.
3. Download `student-mat.csv` from the [UCI dataset page](https://archive.ics.uci.edu/dataset/320/student+performance).
4. Upload the CSV file when prompted by the notebook, or place it in the configured data directory.
5. Run the notebook cells in order.
6. Review the EDA visualizations, model training curves and evaluation results.

### Option 2: Run Locally

Clone the repository:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_PROJECT_FOLDER>
```

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow jupyter
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open the notebook and execute the cells in sequence. Ensure that the dataset path matches the location of `student-mat.csv`.

## 📁 Repository Structure

```text
student-mathematics-performance/
│
├── README.md
├── student_mathematics_performance.ipynb
├── report.pdf
└── .gitignore
```

*The structure above is a suggested organization. Include only the files that actually exist in your repository.*

## ⚠️ Limitations

- The dataset contains a limited number of student records.
- Relationships identified in the data do not necessarily imply causation.
- Performance may vary with the train/test split, features and model hyperparameters.
- Previous grades are strong potential predictors and may not be available in every early-intervention scenario.
- The model should not be used as the sole basis for educational decisions about individual students.

## 🔮 Future Enhancements

- Compare MLP performance with Logistic Regression, Decision Trees and Random Forests.
- Perform hyperparameter tuning and cross-validation.
- Apply explainable AI methods to understand feature contributions.
- Investigate class imbalance and alternative classification metrics.
- Develop an interactive dashboard for exploring student performance.
- Evaluate generalization on additional educational datasets.

## 📚 References

1. Cortez, P., & Silva, A. (2008). *Using data mining to predict secondary school student performance.* UCI Machine Learning Repository. https://archive.ics.uci.edu/dataset/320/student+performance
2. McKinney, W. (2010). Data structures for statistical computing in Python. *Proceedings of the 9th Python in Science Conference.*
3. Pedregosa, F., et al. (2011). Scikit-learn: Machine learning in Python. *Journal of Machine Learning Research, 12*, 2825–2830.
4. Abadi, M., et al. (2016). TensorFlow: A system for large-scale machine learning. *12th USENIX Symposium on Operating Systems Design and Implementation.*

## 👩‍💻 Author

**Prarthana S**

B.Tech — Artificial Intelligence and Data Science

KPR Institute of Engineering and Technology

**Course:** U21ADP05 — Exploratory Data Analysis and Visualization (Assignment II)

---

## 📄 Disclaimer

This project is developed for academic purposes. The analysis and predictions are experimental and should not be interpreted as definitive assessments of a student's ability or future academic performance.
