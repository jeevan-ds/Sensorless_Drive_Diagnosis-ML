# Sensorless_Drive_Diagnosis-ML
 <img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/bb0ecaa9-f0e5-4791-ac2e-8ca60be9fc05" />


#  Sensorless Drive Diagnosis using Machine Learning

##  Project Overview
Electric motors are a critical component of modern industrial systems, powering applications such as conveyors, pumps, compressors, and robotic equipment. Unexpected motor failures can result in costly downtime and operational risks.

Traditional motor condition monitoring relies on physical sensors, which increase system cost and maintenance complexity. To overcome these limitations, industries increasingly adopt **sensorless drive systems**, where motor operating conditions are inferred using electrical signals instead of physical sensors.

This project develops a **machine learning-based sensorless diagnostic system** that classifies motor operating conditions using electrical signal data, enabling reliable and cost-effective condition monitoring.

---

##  Problem Statement
The objective of this project is to **predict the operating condition of an electric motor drive using only electrical signal measurements**, without relying on physical sensors.

This is formulated as a **multi-class classification problem**, where each data instance belongs to one of **11 distinct motor operating conditions**.

---

##  Industry Relevance
This project is relevant to:
- Smart Manufacturing (Industry 4.0)
- Predictive Maintenance
- Industrial Automation
- Power Electronics and Motor Drives

A sensorless diagnostic system can help industries:
- Reduce dependency on physical sensors
- Detect abnormal operating conditions early
- Minimize unplanned downtime
- Lower maintenance and hardware costs

---

## Dataset
- **Source:** UCI Machine Learning Repository  
- **Dataset:** Sensorless Drive Diagnosis  
- **Total instances:** 58,509  
- **Features:** 48 continuous numerical variables  
- **Target:** Motor operating condition (11 classes)

The input features represent **pre-engineered electrical and control-related signals**, reflecting real industrial data where exact sensor semantics are often abstracted due to confidentiality.

---

## Methodology

###  Data Preparation
- Loaded space-separated industrial data
- Assigned structured feature names
- Verified data quality and class balance

### Exploratory Data Analysis (EDA)
- Analyzed feature distributions and scale differences
- Identified strong correlations among electrical signals
- Confirmed the need for feature scaling and non-linear models

###  Model Development
- **Logistic Regression** used as a linear baseline
- **Random Forest Classifier** used to capture non-linear relationships

###  Model Evaluation
- Train–test split for initial assessment
- **5-fold cross-validation** for reliable generalization performance
- Confusion matrices and class-wise metrics for detailed analysis

---

##  Experimental Results

| Model | Cross-Validation Accuracy |
|-----|---------------------------|
| Logistic Regression | ~75% |
| Random Forest (depth-constrained) | ~77% |

Unconstrained models achieved near-perfect accuracy on a single split; however, cross-validation revealed that such results were optimistic due to overfitting. A **depth-constrained Random Forest** was selected as the final model to ensure reliable generalization.

---

##  Key Insights
- Electrical signal patterns are highly informative but partially overlapping across certain motor operating conditions
- Perfect classification is limited by inherent similarities in motor behavior
- Honest evaluation using cross-validation is critical for industrial reliability
- Feature importance analysis shows that only a subset of signals dominates diagnosis

---

##  How This System Is Used in Industry
In real industrial environments, this type of model is deployed as a **decision-support system**, not a standalone fault detector.

### Typical Workflow:
1. Electrical signals are continuously collected from motor drives
2. Features are extracted in real time
3. The trained model predicts the motor operating condition
4. Predictions are mapped to risk levels (normal, warning, abnormal)
5. Engineers use these insights to plan maintenance and reduce downtime

---

##  Final Conclusion
This project demonstrates the practical application of machine learning for sensorless motor drive diagnosis using electrical signal data. By combining systematic experimentation, cross-validation, and controlled model complexity, a robust and interpretable solution was developed with approximately **77% generalization accuracy**.

The results emphasize that **robustness, interpretability, and realistic performance estimates** are more valuable than artificially high accuracy in industrial machine learning applications.



