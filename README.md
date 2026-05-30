# Money Laundering Detection Using Machine Learning

A machine learning project that identifies potentially suspicious financial transactions associated with money laundering activities.

This project was developed as part of the Decodelabs Data Science Internship, where participants were responsible for selecting a real-world dataset, performing exploratory data analysis, building predictive models, and generating business-focused insights.

---

## Project Overview

Financial institutions process millions of transactions every day, making manual monitoring for money laundering activities extremely difficult.

This project uses machine learning techniques to classify financial transactions as either legitimate or potentially suspicious using transaction-level features from a large synthetic Anti-Money Laundering (AML) dataset.

The model is optimized to maximize the detection of laundering activity while handling the severe class imbalance commonly found in financial crime datasets.

---

## Business Problem

Money laundering is used to disguise illegally obtained funds and is often linked to fraud, organized crime, corruption, and terrorism financing.

Banks and financial institutions must continuously monitor transactions and report suspicious activity to regulatory authorities.

Traditional rule-based systems frequently generate excessive alerts and struggle to adapt to evolving laundering patterns.

This project demonstrates how machine learning can support compliance teams by automatically identifying high-risk transactions for further investigation.

---

## Business Impact

### High Detection Capability

The model achieves approximately **94% recall** for laundering transactions, meaning it successfully identifies most suspicious transactions in the dataset.

### Compliance Support

The system can help:

* Reduce manual transaction screening
* Prioritize investigations
* Improve regulatory compliance
* Support risk-based monitoring workflows

### Risk Scoring

Predicted probabilities can be used as risk scores, allowing compliance teams to define investigation thresholds based on operational capacity.

---

## Dataset

### Source

IBM Anti-Money Laundering Synthetic Dataset

Dataset File:

```text
HI-Small_Trans.csv
```

### Dataset Characteristics

| Feature              | Value                            |
| -------------------- | -------------------------------- |
| Rows                 | 5,078,345                        |
| Columns              | 11                               |
| Target Variable      | Is Laundering                    |
| Positive Class Ratio | ~0.1%                            |
| Dataset Type         | Synthetic Financial Transactions |

### Target Variable

| Value | Meaning                      |
| ----- | ---------------------------- |
| 0     | Legitimate Transaction       |
| 1     | Money Laundering Transaction |

> Note: This dataset is synthetic and intended for educational and research purposes.

---

## Technologies Used

### Programming Language

* Python

### Data Processing

* pandas
* NumPy

### Data Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn
* XGBoost

### Development Tools

* Jupyter Notebook
* VS Code
* Git
* GitHub

---

## Repository Structure

```text
aml-transaction-classfier-python/
│
├── images/
│   ├── aml_full_plots.png
│   └── ...
│
├── aml_analysis.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Installation

### Clone Repository

```bash
git clone https://github.com/MDX2002/aml-transaction-classfier-python.git

cd aml-transaction-classfier-python
```

### Create Virtual Environment

Windows:

```bash
python -m venv venv

venv\Scripts\activate
```

Linux/macOS:

```bash
python -m venv venv

source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Running the Project

Place the dataset file inside your working directory and open:

```text
aml_analysis.ipynb
```

Run all notebook cells sequentially.

---

## Project Workflow

### 1. Data Preprocessing

* Removed non-predictive identifiers
* Converted timestamps into usable features
* Encoded categorical variables
* Handled extreme class imbalance

### 2. Exploratory Data Analysis

Performed analysis on:

* Class distribution
* Transaction amounts
* Transaction timing patterns
* Feature correlations
* Currency and payment format distributions

### 3. Machine Learning Model

Algorithm Used:

```text
XGBoost Classifier
```

Key Parameters:

```python
XGBClassifier(
    n_estimators=100,
    max_depth=6,
    scale_pos_weight=<calculated>,
    tree_method="hist"
)
```

Training Split:

```text
80% Training
20% Testing
```

---

## Model Performance

| Metric                 | Score  |
| ---------------------- | ------ |
| ROC-AUC                | 0.9686 |
| Recall (Laundering)    | 94%    |
| Precision (Laundering) | 1%     |
| False Positive Rate    | 1.3%   |

### Interpretation

The model demonstrates excellent separation between legitimate and suspicious transactions.

For AML systems, maximizing recall is often more important than maximizing precision because missing criminal activity can have severe financial and regulatory consequences.

---

## Visualizations

The project includes exploratory data analysis visualizations stored inside the `images/` folder.

Examples include:

* Class distribution
* Transaction amount distribution
* Hour-of-day transaction analysis
* Feature correlation heatmaps

---

## Key Findings

* Payment formats strongly influence laundering predictions.
* Certain transaction timing patterns correlate with suspicious activity.
* Extreme class imbalance significantly affects model design choices.
* Cost-sensitive learning helps improve detection performance without oversampling.

---

## Future Improvements

### Reduce False Positives

* Threshold optimization
* Ensemble methods
* Two-stage classification pipelines

### Advanced Feature Engineering

* Transaction velocity features
* Historical account behavior
* Rolling transaction statistics

### Graph-Based AML Detection

* Transaction networks
* Community detection
* Relationship analysis between accounts

### Real-Time Deployment

* FastAPI prediction service
* Dashboard monitoring
* Streaming transaction scoring

---

## Internship Context

This project was completed as part of the DecodeLabs Data Science Internship program.

Participants were provided with a project framework and were responsible for:

* Selecting datasets
* Performing analysis
* Building predictive models
* Generating business insights
* Presenting results in a professional portfolio format

---

## License

This project is intended for educational and portfolio purposes.

---

## Acknowledgements

* IBM for providing the synthetic AML dataset
* DecodeLabs for internship guidance
* Open-source Python community

---

Built using Python, XGBoost, pandas, NumPy, and Scikit-learn.
