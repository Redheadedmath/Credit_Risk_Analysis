# Credit_Risk_Analysis

## Analysis Overview
The scope of this analysis covers a variety of ML models to predict whether a loan applicant is at high or low risk of defaulting on thier debts. The analysis utilizes a combination of over- and under-sampling methods *RandomOverSampler, SMOTE, CluserCentroids* and the combined *SMOTEEN* before using **SKLearn's** LogisticRegression model to predict risk level from more than 80 features. These methods are compared to two **imblearn** ensemble classifiers *BalancedRandomForest* and *EasyEnsemble*.

### Constraints
- 85 Factors, 1 target variable (risk level)
- Highly Imbalanced:
  - 68,470 'low_risk' data points
  - 347 'high_risk' data points

## Results
In the table below, the reports for the six ML models are depicted including: their balanced accuracy scores, precision and recall scores, confusion matrix, and classification report (with F1 score). <br />

<table style='width: 100px'>
  <tr>
    <th>Random Oversampling</th>
    <th>Synthetic Minority Oversampling Technique (SMOTE)</th>
    <th>SMOTE + Edited Nearest Neighbors (SMOTEENN)</th>
  </tr>
  <tr>
    <td> <img src="Resources/ROS_scores.png" alt="Random Oversampling Report" style="width: 33.3px"/></td>
    <td> <img src="Resources/SMOTE_scores.png" alt="SMOTE Report" stlye="width: 33.3px"/></td>
    <td> <img src="Resources/SMOTEENN_scores.png" alt="SMOTEENN Report" style="width: 33.4px"/></td>
  </tr>
  <tr>
    <th>Cluster Centroids</th>
    <th>Balanced Random Forest</th>
    <th>Easy Ensemble Classifier</th>
  </tr>
  <tr>
    <td> <img src="Resources/CC_scores.png" alt="Cluster Centroids Report" style="width: 33.3px"/></td>
    <td> <img src="Resources/BRF_scores.png" alt="BRF Report" stlye="width: 33.3px"/></td>
    <td> <img src="Resources/eensemble_scores.png" alt="Easy Ensemble Report" style="width: 33.4px"/></td>
  </tr>
</table>

## Summary
Certainly, no model is perfect. There are limitations and the field of statistics is the balancing act of what is accurate and precise with what is practical. There is certainly a balancing act with these models. The chief limitation of these models is the limited access to 'high_risk' data, hence the various over- and undersampling methods employed to compensate. Each of the above models risks misclassifying 'high_risk' clients. <br />
In order to choose the best model, or to build a pipeline with a combination of these models, the auditors would need to decide which metric is most meaningful--albeit accuracy, sensitivity/recall, or the balanced F1 scores. Given the nature of this data set, I would value the recall, or sensitivity, of the model most--the ability of the model to identify true 'high_risk' clients. This minimizes the lender's risk. <br />

### Recommendation
As such, I would recommend the EasyEnsemble model for the institution's ML pipeline. It offers the highest scores (F1 = 0.16, Recall (HR) = 0.94) of all the reports and has an excellent recall score for both 'low_risk' and 'high_risk' clients. Additionally, the Balanced Random Forest model performs well enough that I would recommend it for a pipeline of the institution. 