#  Helicopter Turbine Engine Fault Classification & Predictive Maintenance

Machine learning binary classification pipeline in **Python** detecting turbine engine anomalies and degradation states using sensor telemetry from the **PHM North America 2024 Data Challenge**.

---

##  Project Overview
* **Objective:** Classify whether a helicopter turbine engine is in a nominal operational state (0) or defective state (1) based on multi-channel flight telemetry to prevent catastrophic in-flight failures.
* **Telemetry Features:** Outside air temperature (OAT), mean gas temperature, indicated airspeed, net power, compressor speed, torque margin, and power available.
* **Models Evaluated:** Logistic Regression (SAGA solver with feature scaling) vs. Random Forest Classifier (100 estimators).
* **Stack & Libraries:** Python, `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`.

---

##  Workflow & Architecture
1. **Preprocessing & Cleaning:** Feature-label parsing, whitespace normalization, and target extraction.
2. **Stratified Sampling:** 80/20 train-test split with class stratification to maintain fault distribution across sets.
3. **Standardization:** Applied standard scaling (`StandardScaler`) to normalize high-variance aerodynamic and thermal sensor readings.
4. **Model Benchmarking:** Evaluated precision, recall, F1-score, and ROC AUC metrics across 148,500+ test records.

---

##  Benchmark Results

| Model | Precision (Class 1) | Recall (Class 1) | F1-Score (Class 1) | Overall Accuracy | ROC AUC |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Logistic Regression** | 0.93 | 0.90 | 0.92 | 94% | 0.9765 |
| **Random Forest Classifier** | **1.00** | **1.00** | **1.00** | **100%** | **0.9999** |

---

##  Engineering & Operational Applications
* **Aerospace Condition Monitoring:** Real-time health scoring based on torque margin deviation from baseline design limits.
* **Fleet Maintenance Optimization:** Automated fault detection reducing unscheduled depot-level maintenance and downtime.

---

## 📁 Repository Structure
* `Turbine_Engine_Fault_Classification.ipynb` — Complete end-to-end Python pipeline from preprocessing to ROC/AUC evaluation.
