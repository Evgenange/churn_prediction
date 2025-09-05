#  Customer Churn Prediction

An end-to-end data science project analyzing the **Telco Customer Churn (IBM)** dataset using **Python, SQL, and Machine Learning**.  

The project demonstrates skills in:
- **Python (EDA & feature engineering)**
- **SQL for business insights**
- **Machine Learning pipelines (scikit-learn & XGBoost)**
- **Model evaluation and comparison with imbalanced data**

---

##  Project Workflow

1. **Exploratory Data Analysis (Python)**  
   - Data cleaning and preprocessing  
   - Statistical tests (Chi-square, correlations)  
   - Visualizations of churn patterns  

2. **SQL Analysis**  
   - Querying churn rates by tenure, services, and payment methods  
   - Generating business insights using SQL aggregations  

3. **Machine Learning Models**  
   - Logistic Regression (baseline + tuned)  
   - Gradient Boosting (baseline + tuned)  
   - HistGradientBoosting (tuned)  
   - XGBoost (baseline + tuned)  

4. **Model Evaluation**  
   - Accuracy, Recall, ROC-AUC  
   - Confusion matrices  
   - ROC and Precision-Recall curves  

---

##  Dataset

The project uses the **Telco Customer Churn (IBM)** dataset, available on Kaggle:  
 [Telco Customer Churn (IBM)](https://www.kaggle.com/datasets/yeanzc/telco-customer-churn-ibm-dataset)

**Dataset details:**
- **7,043 customers** from a telecom provider  
- **33 features**: demographics, account information, contract type, charges, and services (internet, streaming, tech support, etc.)  
- **Target variable:** `Churn` (Yes/No), indicating whether the customer left  
- **Class imbalance:** ~27% churn vs ~73% no churn  

 The dataset is **not included** in this repository to respect Kaggle licensing.  
Please download it manually and place it in the `data/` folder before running the notebooks.  

---

## Repository Structure

- data/ # place dataset here(not included)
- notebooks/ 
    1. python_eda.ipynb #Exploratory Data Analysis (Python)
    2. sql_analysis.ipynb #SQL-based churn insights
    3. ml_models.ipynb # Machine Learning & Evaluation

- requirements.txt
- README.md # Project Documentation
- LICENSE # MIT licence

---

## Results (Test Set)

| Model                  | Accuracy | Recall | ROC-AUC |
|------------------------|----------|-------|----------|
 Logistic Regression      0.73      **0.85**     0.84  
 Gradient Boosting        0.80        0.50       0.84    
 HistGradientBoosting     0.80        0.49     **0.85** 
 XGBoost                  0.71        0.83       0.84    

---

## Key Takeaways
- **Imbalanced dataset** (~27% churn) : recall is more important than accuracy.  
- **Logistic Regression & XGBoost**: catch most churners (high recall) but more false positives.  
- **GB & HistGB**: higher accuracy, fewer false positives, but miss many churners (low recall).  
- **All models generalized well** (AUC ~0.84–0.85, no overfitting).  

**Best choice depends on business priorities**:  

- If avoiding missed churners is critical : **Logistic Regression / XGBoost**  
- If balancing recall and precision is preferred : **Gradient Boosting / HistGB**  

---

## License
This project is licensed under the MIT License — see [LICENSE](LICENSE).  
