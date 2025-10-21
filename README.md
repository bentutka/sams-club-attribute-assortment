# Attribute-Based Assortment  
*University of Arkansas – Data Science Practicum II (DASC 49903)*  
*In collaboration with Sam’s Club, a Division of Walmart Inc.*

---

## Overview
This project was developed in partnership with **Sam’s Club** as part of the **University of Arkansas Data Science Practicum II**.  
Our objective was to create a **data-driven, bottom-up framework** for optimizing item assortments across nearly **600 Sam’s Club locations** in the United States and Puerto Rico.  

Using machine learning and demographic data, we analyzed how store-level attributes influence sales across product subcategories, identifying actionable insights for more localized, efficient assortment planning.

> **Note:** Certain datasets, visuals, and implementation details are **intentionally masked or omitted** due to a **non-disclosure agreement (NDA)** with Sam’s Club.

---

## Project Problem & Goal
Sam’s Club faces the challenge that **item performance varies greatly between stores**, and product assortments are not always optimally allocated.  

Using **machine learning techniques**, our goal was to:
- Recommend better-performing items for each club  
- Base recommendations on **club attributes, sales data, and customer demographics**  
- Help inform future **inventory and space optimization** strategies  

---

## Data Preview
The dataset included:
- Point-of-Sale (POS) sales data  
- Club attributes and demographic information  
- Engineered features such as population density, income levels, competition proximity, and climate zones  

All raw data originated from Sam’s Club’s internal systems, supplemented with external data from the **U.S. Census Bureau**, **Federal Reserve Economic Data (FRED)**, and **Kaggle (stadium datasets)**.

> Proprietary data tables and figures have been redacted in accordance with NDA protections.

---

## Project Process
The project followed a structured, iterative workflow:

1. **Related Research** – Reviewed industry literature (McKinsey, Kroger KASpR, 84.51°) on assortment optimization  
2. **Data Collection & Preparation** – Aggregated and cleaned internal and external datasets  
3. **Exploratory Data Analysis** – Investigated sales trends, seasonal cycles, and store-level differences  
4. **Data Modeling** – Built and compared multiple machine learning models  
5. **Understanding Models** – Interpreted feature importances across product categories  
6. **Drawing Conclusions** – Synthesized insights for Sam’s Club’s future retail strategy  

---

## CatBoost Model
The **CatBoost** machine learning model was selected for its ability to handle both categorical and numerical features efficiently.  
It reduces overfitting and avoids complex user-encoding requirements.

Our models:
- Predicted **subcategory sales** as a **proportion of total club sales**
- Used combinations of club attributes, sales data, and demographics as predictors
- Produced interpretable **feature importances** for every subcategory

Each model was trained and executed in **PySpark on Databricks**, enabling parallel processing across hundreds of subcategories.  
Variable importances were stored as `.pkl` files for aggregation and analysis.

---

## Results & Conclusions
We compiled all feature importances into a unified dataframe and analyzed them by **General Merchandise Management (GMM)** category.  
This allowed for deeper insight into which variables were more influential for specific product groups.

**Key findings:**
- Features such as **population density**, **median income**, and **competition proximity** showed varying importance across subcategories.  
- Certain **regional and climate-based variables** played a strong role in predicting item sales.  
- Outlier subcategories, where specific features had unusually high influence, provided actionable insight for localized inventory management.

This level of analysis supports:
- Improved inventory decisions at the **store or cluster level**
- Strategic guidance for **item additions/removals**
- Long-term category-level recommendations for **space and assortment optimization**

---

## Future Work
- Validate hypotheses on which features are most predictive of sales  
- Expand analyses to include **surrounding ZIP codes** (to capture non-local shoppers)  
- Explore **cross-category interactions** and **multi-GMM correlations**  
- Incorporate improved model performance metrics for next-phase development  

---

## Team
**University of Arkansas Team**  
- Benjamin Tutka  
- Noa Scharf  
- Hector Negron  

**Sam’s Club Team**  
- Michael Juang – Principal Data Scientist  
- Nikhil Sharma – Data Scientist  
- Ada Shi – Director, AI  

**Faculty Advisor:** Dr. Schubert  

---

## References
- U.S. Census Bureau (2023). *Census Datasets.* https://www.census.gov/data/datasets.html  
- McKinsey & Company (2019). *Retail Analytics and Advanced Assortment Optimization.*  
- 84.51° (n.d.). *Optimizing Store Space with Machine Learning.* https://www.8451.com/knowledge-hub/technology/optimizing-store-space-with-machine-learning  

---

## Visual Summary
Below is the team’s final presentation poster summarizing the workflow, modeling, and conclusions:

![Practicum Poster – Team 07](Practicum%20Poster%20-%20Team%2007-2.png)

---

## NDA Disclaimer
All information, data, and code in this repository have been reviewed to comply with **Sam’s Club’s confidentiality and data protection agreements**.  
Sensitive identifiers, metrics, and visuals have been removed or masked.  
The repository is intended solely for **academic and illustrative purposes**.
