This documentation provides a full overview of the thesis project **"Auditing and Assessing the Wireless Network Attacks Using Machine Learning"**, including setup instructions and detailed module breakdowns.
 
# Setup Instructions:
## 1. Clone the Repository
gh repo clone jayanth27shiva/capstone2025-jeyadevaswamy-Auditing-and-Assessing-Wireless-Networks-using-ML-Techniques

## 2. Install Required Packages
Install all dependencies listed in the requirements file:
pip install -r requirements.txt

## 3. Launch the Notebook
jupyter notebook IDS_TEMPORARY.ipynb
Open the file and run cells step-by-step.

# Project Workflow & Module Descriptions
1. Data Loading & Extraction
- Reads wireless traffic dataset (CSV or ZIP)
- Extracts files if zipped
- Loads training and test sets into Pandas DataFrames

2. Preprocessing
- Encodes categorical variables (e.g., protocol_type, service)
- Normalizes numerical features using MinMaxScaler
- Drops irrelevant or non-numeric fields
- Prepares X_train, X_test, y_train, y_test for model input

3. Feature Selection
Techniques used:
- SelectKBest with chi2 or mutual_info_classif
- Identifies most influential features to improve training efficiency and accuracy
- Compares performance before and after selection

4. Model Training
Models used:
- Logistic Regression
- Random Forest Classifier
- Autoencoder (for zero-day anomaly detection)

5. Evaluation & Metrics
Metrics used:
- Accuracy
- Precision, Recall, F1 Score
- Confusion Matrix
- ROC Curve and AUC
- False Positive Rate (FPR)

6. Zero-Day Detection (Autoencoder)
- Trained only on “normal” data
- Calculates reconstruction error for each test sample
- Uses a dynamic threshold (e.g., 99.9 percentile) to flag anomalies
- Combines with classifier for final verdict

7. Visualization 
Plots generated:
- Training vs. Validation Accuracy/Loss 
- Confusion Matrix 
- ROC Curves with AUC
- Feature Importance (Random Forest)

Precision-Recall Curves

Reconstruction Error Distribution (for Autoencoder)
