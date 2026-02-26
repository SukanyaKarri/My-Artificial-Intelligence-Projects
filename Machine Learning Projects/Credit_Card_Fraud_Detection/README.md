## Credit Card Fraud Detection

### Project Overview
- This project focuses on detecting fraudulent credit card transactions using supervised machine learning techniques. The dataset contains anonymized transaction features obtained through PCA transformation along with transaction amount, time, and a binary fraud indicator.
- The objective is to build and evaluate classification models capable of identifying fraudulent transactions in a highly imbalanced dataset.

### Dataset

**Source:**  
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud  

The dataset contains:
- **Time** – Seconds elapsed between transactions  
- **V1 to V28** – PCA-transformed numerical features  
- **Amount** – Transaction amount  
- **Class** – Target variable  
  - 0 → Legitimate transaction  
  - 1 → Fraudulent transaction  

The dataset is highly imbalanced, with fraudulent transactions representing a very small percentage of total observations.

### Project Requirements
- Perform exploratory data analysis (EDA)
- Handle class imbalance appropriately
- Build classification models for fraud detection
- Evaluate models using suitable performance metrics for imbalanced data
- Interpret model performance and derive meaningful insights

### Exploratory Data Analysis

The analysis included:
- Distribution analysis of transaction amount and time
- Class imbalance examination
- Correlation study between features
- Identification of potential outliers
- Visualization of fraud vs non-fraud transaction patterns

#### Key Observations
- Fraudulent transactions represent a very small minority of total transactions.
- Certain PCA components show distinguishable distribution patterns between fraud and non-fraud classes.

### Data Preparation

The following preprocessing steps were applied:
- Feature scaling (where required)
- Train-test split
- Handling severe class imbalance using appropriate strategies
- Evaluation metric selection aligned with fraud detection objectives

Given the imbalance, accuracy alone was not considered a reliable performance metric.

### Models Implemented

The project includes implementation and evaluation of:
- Logistic Regression
- Additional classification approaches explored within the notebook

Model evaluation focused on:
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix

### Evaluation Approach

Due to the imbalanced nature of the dataset:
- Recall for the fraud class was prioritized.
- ROC-AUC was used as a threshold-independent performance metric.
- Confusion matrix analysis was performed to understand false positives and false negatives.

Fraud detection systems must minimize false negatives while maintaining manageable false positives.

### Insights Observed
- The dataset is highly imbalanced, requiring careful evaluation strategy.
- Certain PCA-transformed variables contribute more significantly to class separation.
- Traditional accuracy metrics can be misleading in fraud detection problems.
- Threshold tuning plays a critical role in balancing precision and recall.

### Project Structure
Credit_Card_Fraud_Detection/
   - CreditCard_Fraud_Detection_CapstoneSubmission_SukanyaKarri.ipynb
   - README.md

### Conclusion
- This project demonstrates a structured approach to solving an imbalanced classification problem in financial fraud detection. The workflow emphasizes proper evaluation methodology, model comparison, and interpretation of classification performance in real-world scenarios.
