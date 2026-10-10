# airlines-clustering-analysis-svd
Unsupervised clustering analysis on East-West Airlines dataset to segment customers and identify travel patterns using K-Means.


# East-West Airlines Customer Segmentation & Clustering Analysis

## 1. Business Problem
### 1.1. What is the business objective?
The primary business objective is to analyze customer frequent flyer and mileage data from East-West Airlines to identify meaningful customer segments (clusters). By grouping customers based on their mileage accumulation, flight activity, and award usage, the airline can design targeted marketing campaigns, optimize loyalty reward programs, and improve customer retention strategies for high-value segments.

### 1.2. Are there any constraints?
* **Data Quality & Outliers:** Frequent flyer datasets often contain extreme outliers (e.g., ultra-high mileage members or corporate accounts) that can skew distance-based clustering algorithms like K-Means.
* **Feature Scaling:** Variables measured on different scales (e.g., total miles vs. months enrolled) require rigorous normalization so that features with larger numerical ranges do not disproportionately dominate the distance calculations.
* **Interpretability:** The resulting clusters must be actionable and easily interpretable by the marketing team to formulate targeted campaigns.

---

## 2. Data Dictionary
*(Replace or adjust descriptions based on your specific columns in `EastWestAirlines.xlsx`)*

| Feature Name | Data Type | Description |
| :--- | :--- | :--- |
| **ID** | Integer | Unique identifier for the frequent flyer. |
| **Balance** | Numeric | Number of miles eligible for award travel. |
| **Qual_miles** | Numeric | Miles qualifying for topflight status. |
| **cc1_miles** | Categorical/Integer | Miles earned with freq. flyer credit card under employee 1 (1: under 5k, 2: 5k-10k, 3: 10k-25k, 4: 25k-50k, 5: over 50k). |
| **cc2_miles** | Categorical/Integer | Miles earned with freq. flyer credit card under employee 2. |
| **cc3_miles** | Categorical/Integer | Miles earned with freq. flyer credit card under employee 3. |
| **Days_since_enroll** | Integer | Number of days since enrollment in the frequent flyer program. |
| **Award** | Binary (0/1) | Indicator of whether the user had a free award flight (0 = No, 1 = Yes). |

---

## 3. Exploratory Data Analysis (EDA)
* **3.1. Summary:** Statistical overview of the dataset including measures of central tendency, spread, and missing value checks.
* **3.2. Univariate Analysis:** Distribution analysis of individual features (e.g., skewness in mileage balances, spread of enrollment tenure).
* **3.3. Bivariate Analysis:** Correlation matrices and scatter plots examining relationships between variables (e.g., flight activity vs. credit card usage).

---

## 4. Data Pre-processing
* **4.1. Data Cleaning & Feature Engineering:** Handled missing values, treated outliers using clipping/transformation, and dropped unnecessary identifier columns. 
* **Normalization:** Applied standard scaling techniques (StandardScaler / MinMaxScaler) to ensure all features contribute equally to the distance metrics used in clustering.

---

## 5. Model Building
* **5.1. Scaled Data Modeling:** Implemented unsupervised learning models on the normalized feature set.
* **5.2. K-Means Clustering & Scree Plot:** Utilized the Elbow Method (Scree Plot / Within-Cluster Sum of Squares) to determine the optimum number of clusters ($k$).
* **5.3. Cluster Validation & Insights:** Validated performance across multiple values of $k$, assigned descriptive business labels to each cluster, and derived comparative insights.

---

## 6. Business Benefits & Impact
The deployment of this customer segmentation solution provides tangible value to the business:
* **Targeted Marketing:** Allows the marketing team to tailor promotions specifically for high-balance, low-activity members versus frequent flyers.
* **Optimized Rewards:** Helps structure loyalty tiers and credit card partner offers to maximize engagement.
* **Churn Prevention:** Identifies disengaged customer segments with high balances, allowing proactive retention campaigns.
