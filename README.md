# Credit Risk Assessment and Data Analysis

## 🔍 Project Overview
A complete end-to-end pipeline that analyzes applicant demographics and credit behavior to predict default risk. We clean and merge application & credit records, engineer meaningful features, and compare multiple machine learning models—delivering a high-accuracy, interpretable credit scoring tool.

## 🎯 Motivation & Goals
Financial institutions wrestle with balancing growth and risk. This project:

- Unearths hidden patterns in large-scale credit data  
- Builds transparent models to flag high-risk applicants early  
- Targets ≥ 90% classification accuracy with explainable techniques  
- Demonstrates full ML lifecycle: data wrangling → modeling → tuning → evaluation

## 🗂 Table of Contents
1. [Installation](#-installation)  
2. [Usage](#-usage)  
3. [Project Structure](#-project-structure)  
4. [Data & Preprocessing](#-data--preprocessing)  
5. [Methodology](#-methodology)  
6. [Results & Evaluation](#-results--evaluation)  
7. [Screenshots](#-screenshots)  
8. [Tech Stack](#-tech-stack)  
9. [Future Work](#-future-work)  
10. [Contributing](#-contributing)  
11. [License](#-license)  
12. [Contact](#-contact)

---

## 🔧 Installation

Clone the repo:

```bash
git clone https://github.com/yourusername/credit-risk-assessment.git
cd credit-risk-assessment
```

Create a virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## 🚀 Usage

### Locally
```bash
jupyter notebook CreditRiskAssessment.ipynb
```

### On Google Colab  
Click the badge at the top to launch in Colab with zero setup.

Make sure your `data/` directory contains:
- `application_record.csv`
- `credit_record.csv`

## 📁 Project Structure

```
credit-risk-assessment/
├── data/
│   ├── application_record.csv   # raw applicant profiles
│   └── credit_record.csv        # month-by-month repayment status
├── images/                      # visualizations for README
│   ├── heatmap.png
│   ├── target_dist.png
│   └── model_comparison.png
├── CreditRiskAssessment.ipynb   # Jupyter analysis & modeling
├── requirements.txt             # Python dependencies
└── README.md                    # this file
```

## 📊 Data & Preprocessing

### `application_record.csv`
- **Rows:** 438,557 | **Columns:** 18  
- **Demographics:** gender, family status, housing  
- **Financials:** income, employment duration, dependents

### `credit_record.csv`
- **Rows:** 1,048,575 | **Columns:** 3  
- Tracks monthly repayment `STATUS` (0–5, C, X) per applicant

### Key Cleaning & Feature Steps
- Dropped duplicates & null-heavy columns  
- Merged on `ID` to link profiles with repayment history  
- Converted `DAYS_BIRTH`, `DAYS_EMPLOYED` → `AGE`, `YEARS_EMPLOYED`  
- Binarized `STATUS`: delinquency flag (`risk_flag = 1` if any status ≥ 2)

## ⚙️ Methodology

### Exploratory Data Analysis
- Distribution plots for income, age, family status  
- Correlation heatmap to spot multicollinearity  
- Class balance assessment

### Feature Engineering
- One-hot encoding for categorical fields  
- Aggregation of repayment behavior (mean, max delay)  
- Scaling numerical features for distance-based models

### Modeling & Tuning
- Employed `GridSearchCV` for hyperparameters  
- 5-fold cross-validation to gauge generalization

### Evaluation Metrics
- Accuracy, Precision, Recall, F1-Score  
- Confusion Matrix & ROC Curve  
- Business-focused thresholds for risk tolerance

## 🏆 Results & Evaluation

| Model                | Accuracy | Precision | Recall | F1 Score |
|---------------------|----------|-----------|--------|----------|
| Logistic Regression |   0.85   |   0.82    |  0.79  |   0.80   |
| Random Forest       |   0.91   |   0.89    |  0.87  |   0.88   |
| Support Vector Machine | 0.83  |   0.81    |  0.76  |   0.78   |
| K-Nearest Neighbors |   0.78   |   0.75    |  0.73  |   0.74   |

📌 Random Forest tops all metrics—ideal for production given its balance of performance and interpretability.

## 📸 Screenshots

```markdown
![Correlation Heatmap](images/heatmap.png)
![Target Distribution](images/target_dist.png)
![Model Accuracy Comparison](images/model_comparison.png)
```

## 🛠 Tech Stack

- **Languages & Tools:** Python 3.9, Jupyter Notebook  
- **Data Handling:** pandas, NumPy  
- **Visualization:** Matplotlib, Seaborn  
- **Modeling:** scikit-learn  
- **Version Control:** Git & GitHub

## 🌱 Future Work

- Integrate XGBoost or LightGBM for boosted performance  
- Address class imbalance via SMOTE or custom class weights  
- Deploy a Streamlit or Flask web demo  
- Implement SHAP or LIME for granular model explanations

## 🤝 Contributing

1. Fork this repo  
2. Create your feature branch: `git checkout -b feature/new-idea`  
3. Commit your changes: `git commit -m 'Add cool feature'`  
4. Push to the branch: `git push origin feature/new-idea`  
5. Open a Pull Request

## 📜 License

This project is licensed under the **MIT License**. See `LICENSE` for details.

## 📬 Contact

**Vinay Trinadh Naraharisetty**  
📧 vinaytrinadh9910@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/VinayTrinadh)  
🔗 [GitHub](https://github.com/VinayTrinadh)  
Feel free to reach out for questions, feedback, or collaboration!