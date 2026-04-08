# SOFE3290_Lab5_100792709 
# SOFE3290 – Lab 5: Data Quality and Validation

## Overview

In this lab, different data quality checks are applied to a dataset to ensure it's reliable and consistent such as:

- Validating data using expectations
- Detecting mislabeled data points
- Identifying anomalous (outlier) values

The lab displays how poor data quality can impact results and how automated tools can help detect and fix these issues. The tasks are to improve data quality using validation rules and machine learning techniques, and detect issues such as incorrect labels, inconsistent values, and anomalies in datasets.  

---

## Task 1 – Data Validation (Great Expectations)

Download Labels.csv and place in content folder for notebook before runtime  

Note: GitHub may show an "Invalid Notebook" preview error for the .ipynb file due to Colab widget metadata. 
The notebook opens and runs correctly in Google Colab. If preview fails, please open the notebook in Colab or Jupyter Notebook.


Three expectations were created to check data quality:

- **Timestamp uniqueness**  
  Ensures each timestamp is unique so every row represents a separate event. Duplicate timestamps indicate logging or duplication issues.

- **Ground Truth availability**  
  Checks that `Ground_Truth_View` is not missing, since it is required for proper comparison and validation.

- **Filename format consistency**  
  Ensures `Occluded_Image_view` follows the format `A_***.png`, keeping naming consistent and avoiding broken references.

---

## Task 2 – Detecting Mislabeled Data (Cleanlab)

Cleanlab was used with a Random Forest model to detect label issues.

- The model identifies data points where the predicted label does not match the given label.
- Example: a point labeled as one class but having feature values closer to another class.
- **Petal length and petal width** were the most influential features causing misclassification.
- These features are strong indicators for class separation, so mismatches suggest labeling errors.

---

## Task 3 – Detecting Anomalies

Anomalies were introduced and detected using Cleanlab.

- Some data points did not follow the usual pattern for their species.
- These points had values outside the expected range or closer to another class.
- **Petal length and petal width** were again the most unusual features.
- These features made anomalies easier to detect since they strongly define class boundaries.

To verify anomalies:
- Compare values with dataset distributions
- Check if values fall outside typical ranges

---

## Repository 

- `Great_Expectations_Task_100792709.ipynb` – Task 1 implementation  
- `CleanLab_Task2_100792709.ipynb` – Mislabeled data detection (Task 2 Implementation)  
- `CleanLab_Task3_100792709.ipynb` – Anomaly detection (Task 3 Implementation)  
- `Labels.csv` – Dataset used  
- Screenshots and outputs included in report  

---

## Summary

This lab shows how important data quality is in machine learning and analysis, and even small issues like incorrect labels or unusual values can affect results. Using tools like Great Expectations and Cleanlab makes it easier to detect and handle these problems efficiently.
