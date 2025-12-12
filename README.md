<img width="1920" height="1080" alt="Health" src="https://github.com/user-attachments/assets/663053e9-998c-4f1a-a64c-738f4457e04c" />

# Cross-Sell Propensity Model — Health to Vehicle Insurance

## Project Overview

This project focuses on developing a **machine learning model to estimate the probability that a health insurance customer will also purchase vehicle insurance**. Using these probabilities, the model generates a **ranked list of customers by purchase propensity**, enabling the company to prioritize commercial contacts and maximize *cross-sell* performance.

The dataset contains **76,220 customers**, reflecting a realistic scenario in the insurance sector: many clients, few buyers, and a high need to identify those most likely to convert. Because the data is **highly imbalanced**, the model was designed to maximize recall of potential buyers while maintaining operational precision.

---

## Business Problem

The goal was to **increase conversion and profitability** in a cross-sell campaign by identifying customers most likely to accept a vehicle insurance offer.

Key challenges included:

* Imbalanced dataset with low natural conversion rate
* High operational cost of contacting uninterested customers
* Need to maximize return without increasing campaign volume
* Ensuring that ranking quality (top-k performance) benefits the business

---

## Solution

A **binary classification propensity model** was developed, leveraging:

* Demographic data
* Customer profile and historical behavior
* Insurance history
* Engineered features (risk, ratios, regional signals, etc.)

The model was optimized using techniques such as:

* Resampling strategies
* Hyperparameter tuning
* Decision threshold optimization
* Ranking metrics (Precision@K, Recall@K, NDCG@K)

**Key performance metrics:**

* **AUC-ROC:** 0.858
* **AUC-PR:** 0.368
* **Optimized F1-score:** 0.4609
* **Recall (positive class):** 76%
* **Precision:** 33%

The strongest advantage of the model is its ability to **rank customers by probability**, allowing the company to contact only the **top 20% most likely** customers—dramatically improving campaign ROI.

---

## Model Performance

### Classification Report (Optimized Threshold = 0.2312)

| Class            | Precision | Recall | F1-score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.96      | 0.79   | 0.86     | 66,880  |
| 1                | 0.33      | 0.76   | 0.46     | 9,342   |
| **Accuracy**     | —         | —      | **0.78** | 76,222  |
| **Macro Avg**    | 0.64      | 0.77   | 0.66     | 76,222  |
| **Weighted Avg** | 0.88      | 0.78   | 0.81     | 76,222  |

### Confusion Matrix

|        | Pred 0 | Pred 1 |
| ------ | ------ | ------ |
| Real 0 | 52,555 | 14,325 |
| Real 1 | 2,254  | 7,088  |

### Global Metrics

* **AUC-ROC:** 0.8583
* **AUC-PR:** 0.3689

---

## Financial Impact

### Business Scenario (realistic, hypothetical)

* **76,220 total customers**
* Company contacts the **top 20%** ranked by the model → **15,244 customers**

### Cost & Revenue Assumptions

| Item                       | Value (R$) | Description               |
| -------------------------- | ---------- | ------------------------- |
| **Cost per contact**       | 10.00      | Phone, email, CRM action  |
| **Net profit per sale**    | 400.00     | Average profit per policy |
| **Baseline purchase rate** | 15%        | Historical conversion     |

---

### Model Results (Top 20% Ranking)

| Metric            | Value | Interpretation                            |
| ----------------- | ----- | ----------------------------------------- |
| **Precision@20%** | 0.357 | 35.7% of contacted customers buy          |
| **Recall@20%**    | 0.583 | Model captures 58.3% of all buyers        |
| **F1@20%**        | 0.443 | Good balance between precision and recall |
| **NDCG@20%**      | 0.558 | Strong ranking quality                    |

---

### Financial Results

| Scenario            | Net Profit (R$) | Interpretation                   |
| ------------------- | --------------- | -------------------------------- |
| **Without model**   | 762,200.00      | Random contacts                  |
| **With model**      | 2,025,417.13    | Using propensity ranking         |
| **Additional gain** | 1,263,217.13    | Extra profit generated           |
| **ROI vs random**   | 165.73%         | Model increases results by 2.65× |

---

### Executive Summary

> *“Using the propensity model, the campaign profit increased from **R$ 762k to R$ 2.02M**, with the same contact volume.
> This represents **R$ 1.26M in additional profit** and a **165.7% ROI** compared to random targeting.
> The model enables precise focus on customers most likely to convert, multiplying results without increasing cost.”*

---

## Key Takeaways

* The model **transforms an operational process into a profit engine**.
* Even with moderate precision, **high recall** ensures most buyers are captured.
* ROI improves **2.65×** over the baseline strategy.
* The campaign shifts from **volume-based** to **intelligence-driven**, reducing waste and boosting conversion.

---

## Conclusion

This project demonstrates how machine learning can unlock **significant commercial value** in cross-sell operations. By accurately ranking customers by probability of purchase, the model:

* Reduces operational waste
* Increases conversion rates
* Generates more than **R$ 1.26 million** in additional profit
* Makes the cross-sell process **strategic, efficient, and highly profitable**

It showcases the power of **propensity modeling** as a direct value-generation mechanism in real-world business environments.

