# MoneySafe AI - Fraud Detection In Mobile Money & Bank Transactions
## Overview

This project applies **machine learning techniques** to detect fraudulent financial transactions using the **Synthetic Financial Datasets for Fraud Detection** from Kaggle.

The dataset simulates real-world financial transactions at scale, with over **3 million records**, including both legitimate and fraudulent cases. The challenge is that fraud is **rare (<1%)**, making this a highly **imbalanced classification problem**.

The project is motivated by **Kenya’s mobile money ecosystem** (e.g., M-Pesa, Airtel Money, T-Kash), where fraud remains a serious threat to financial inclusion and trust.

---

## Objectives

* Explore the dataset and identify **fraud patterns**.
* Preprocess and balance data for modeling.
* Engineer new features from balances and transaction details.
* Train baseline and advanced ML models (Logistic Regression, Random Forest, XGBoost).
* Evaluate models using metrics suitable for **imbalanced datasets**.
* Provide **practical insights** into fraud detection for mobile money systems.

---

## Dataset

* **Source**: Kaggle – [Synthetic Financial Datasets for Fraud Detection](https://www.kaggle.com/datasets/ealaxi/paysim1) 
* **Size**: \~3.1 million rows
* **Features**:

  * `step`: Time unit of the transaction
  * `type`: Transaction type (cash-in, transfer, cash-out, etc.)
  * `amount`: Transaction value
  * `oldbalanceOrg`, `newbalanceOrig`: Sender’s balance before & after
  * `oldbalanceDest`, `newbalanceDest`: Receiver’s balance before & after
  * `isFraud`: Target variable (1 = Fraudulent, 0 = Legitimate)
  * `isFlaggedFraud`: Flagged by rule-based detection system

---

## Methodology

1. **Data Preprocessing**

   * Encoding transaction type.
   * Normalizing amounts.
   * Handling missing balances.
   * Balancing fraud vs non-fraud (SMOTE, undersampling).

2. **Exploratory Data Analysis (EDA)**

   * Fraud vs non-fraud distribution.
   * Fraud concentration by transaction type.
   * Amount patterns and balance changes.

3. **Feature Engineering**

   * Balance differences (sender & receiver).
   * Transaction-to-balance ratios.
   * Transaction frequency features.

4. **Modeling**

   * Logistic Regression (baseline).
   * Decision Tree.

5. **Evaluation Metrics**

   * Precision
   * Recall
   * F1-score

---

## Results

| **Model**               | **Accuracy** | **Precision** | **Recall** | **F1-Score** | **Notes**                                        |
| ----------------------- | ------------ | ------------- | ---------- | ------------ | ------------------------------------------------ |
| Logistic Regression     | 0.9995       | 0.9482        | 0.4533     | 0.6134       | High precision, low recall (misses many frauds)  |
| Decision Tree (untuned) | 0.9997       | 0.8242        | 0.7771     | 0.8000       | Balanced, better recall than Logistic Regression |
| Decision Tree (tuned)   | 0.9997       | 0.8004        | 0.8248     | 0.8124       | Best overall (improved F1 with tuning)           |

---

## Key Insights

* Fraud is **rare but very costly**.
* **Balance differences** and **high-value transfers** are strong fraud signals.
* Rule-based fraud flags are **not sufficient**.
* ML models, especially **XGBoost**, adapt better to evolving fraud tactics.

---

## Impact & Relevance

* Stronger fraud detection reduces financial losses.
* Builds **trust in mobile money ecosystems** like M-Pesa.
* Supports **SDG 8: Decent Work & Economic Growth**.
* Framework adaptable to banks, fintechs, and mobile money providers.

---

## Future Work

* Apply to **real-world mobile money datasets**.
* Develop **real-time fraud detection system**.
* Incorporate **user/device behavior** features.
* Integrate **Explainable AI (XAI)** for transparency.

---

## Repository Structure

```
fraud-detection-project/
│── data/                 # Dataset (not uploaded, must be downloaded from Kaggle)
│── notebooks/            # Jupyter notebooks for EDA & modeling
│── src/                  # Scripts for preprocessing, models, utils
│── results/              # Visualizations & model outputs
│── README.md             # Documentation
│── requirements.txt      # Dependencies
```

---

## Installation & Usage

1. Clone repository:

   ```bash
   git clone https://github.com/yourusername/fraud-detection.git
   cd fraud-detection
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Run notebooks:

   ```bash
   jupyter notebook
   ```

---

## License

This project is licensed under the MIT License.

---

## Acknowledgments

* Dataset: [Kaggle – Synthetic Financial Datasets for Fraud Detection](https://www.kaggle.com/datasets/ealaxi/paysim1)
* Libraries: Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn




