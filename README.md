# 💳 Credit Card Customer Segmentation & Credit Scoring System

## 📌 Project Overview

This project presents a **complete data mining pipeline** applied to a real-world credit card dataset.
It combines **unsupervised learning, fuzzy logic, and evolutionary optimization** to build an interpretable credit scoring system.

The system analyzes customer behavior and produces a **creditworthiness score** that can support financial decision-making.

---

## 🎯 Objectives

* Discover hidden customer segments using clustering techniques
* Build an interpretable **Fuzzy Logic System** for credit scoring
* Optimize feature selection using a **Genetic Algorithm**
* Develop an end-to-end pipeline for real-world inference

---

## 📊 Dataset

* **Source:** Credit Card Customers Dataset
* **Size:** 8950 customers × 18 features
* **Type:** Behavioral financial data

### Key Features:

* `BALANCE`
* `PURCHASES`
* `CREDIT_LIMIT`
* `PAYMENTS`
* `PURCHASES_FREQUENCY`
* etc.

---

## 🔍 1. Exploratory Data Analysis (EDA)

* Strong **positive skewness** detected in financial features
* Mean vs Median analysis revealed **heavy spending concentration**
* High correlation found between:

  * `PURCHASES` & `ONEOFF_PURCHASES`
* Outliers represent **high-value (VIP) customers**

📌 Insight:

> A small percentage of customers dominates total spending.

---

## ⚙️ 2. Data Preprocessing

* Missing values handled using **median (robust to skewness)**
* **Selective outlier capping** applied only to highly skewed features
* Feature scaling using **StandardScaler**

---

## 📊 3. K-Medoids Clustering

* Evaluated clusters using:

  * **Elbow Method**
  * **Silhouette Score**
* Optimal number of clusters: **K = 3**

### Customer Segments:

1. **VIP Spenders**

   * High balance, high activity
2. **Installment Users**

   * متوسط الإنفاق + اعتماد على التقسيط
3. **Budgeters**

   * Low activity and low spending

---

## 🌲 4. Hierarchical Clustering

* Applied multiple linkage strategies (Ward preferred)
* Ward method selected due to:

  * Better **intra-cluster compactness**
  * More balanced segmentation

---

## 🧠 5. Fuzzy Logic Credit System

A rule-based system that transforms customer behavior into a **credit score**.

### Inputs:

* Purchase Frequency
* Customer Segment (Cluster)

### Output:

* Creditworthiness Score (0–100%)

### Example Rules:

* IF VIP & High Activity → **Prime**
* IF Budgeter & Low Activity → **Low Credit**

📌 Advantage:

> Provides **interpretable decisions**, unlike black-box models.

---

## 🧬 6. Genetic Algorithm Optimization

* Used for **feature selection**
* Fitness function: **Silhouette Score**

### Results:

* Improved clustering quality:

  * From **0.16 → 0.39**

📌 Insight:

> Feature selection significantly enhances unsupervised learning performance.

---

## 🔗 7. System Pipeline

End-to-end system that:

1. Takes a new customer record
2. Applies preprocessing
3. Predicts cluster
4. Runs fuzzy inference
5. Outputs final credit score

---

## 📈 8. PCA (Bonus)

* Used for **visualization only**
* Reduced 17 features → 2 dimensions
* Preserved ~significant variance

📌 Important:

> PCA was NOT used in training to preserve feature interpretability.

---

## 💡 Key Insights

* Customer behavior is highly **skewed and segmented**
* Not all customers should be treated equally in credit decisions
* Combining clustering + fuzzy logic provides:

  * Interpretability
  * Flexibility
* Optimization techniques (GA) improve model quality

---

## 🏁 Conclusion

This project demonstrates how multiple data mining techniques can be integrated into a **practical decision-support system**.

It highlights the importance of:

* Feature engineering
* Model interpretability
* Data-driven customer segmentation

---

## 🛠️ Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* Scikit-fuzzy
* Matplotlib, Seaborn

---

## 🚀 Future Improvements

* Deploy as a web application
* Use real-time streaming data
* Compare with supervised learning models

---

## 👨‍💻 Author

**[Your Name Here]**

---

## ⭐ If you found this project useful, consider giving it a star!
