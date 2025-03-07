# ml glossary

| **Term**                          | **Analysis**                                                                                           | **Metrics Used**                                      |
|------------------------------------|------------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| **Gaussian Naïve Bayes (GaussianNB)** | A probabilistic classifier assuming feature independence, often leading to overconfident predictions. | None (directly, but calibration metrics apply)       |
| **Calibration of Probabilities**  | The process of adjusting predicted probabilities to better reflect true likelihoods.                 | Brier Score Loss, Log Loss                           |
| **Transposed-Sigmoid Curve**      | A miscalibration pattern where the model is overly confident in incorrect predictions.              | Calibration Curve                                    |
| **Isotonic Regression (`isotonic`)** | A non-parametric method for recalibrating probabilities using a piecewise linear mapping.           | Brier Score Loss, Log Loss                           |
| **Sigmoid Regression (`sigmoid_regressor`)** | A parametric method (logistic regression) for probability calibration.                              | Brier Score Loss, Log Loss                           |
| **Brier Score Loss**              | Measures the mean squared difference between predicted and actual probabilities.                     | Lower is better (ranges from 0 to 1)                 |
| **Log Loss (`log_loss`)**         | Evaluates how confident and correct probability estimates are.                                      | Lower is better                                      |
| **Precision, Recall, F1-score**   | Measures classification performance but does not assess probability calibration.                   | Precision, Recall, F1-score                          |
| **ROC AUC (`roc_metrics`)**       | Assesses the ability of the classifier to rank positive instances higher than negative ones.       | Higher is better (ranges from 0 to 1)                |

--- 
### **📌 Classification Metrics**
| **Metric Name**  | **Calculation Formula**  | **Example Understanding**  |
|------------------|-------------------------|----------------------------|
| **Precision**  | \( \text{Precision} = \frac{TP}{TP + FP} \) | If a classifier predicts 100 emails as spam, and 80 of them are truly spam, Precision = 80/100 = 0.8 (80%). |
| **Recall (Sensitivity)**  | \( \text{Recall} = \frac{TP}{TP + FN} \) | If there are 100 spam emails, and the classifier correctly identifies 80, Recall = 80/100 = 0.8 (80%). |
| **F1-score**  | \( F1 = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}} \) | If Precision = 0.8 and Recall = 0.8, then \( F1 = 2 \times \frac{0.8 \times 0.8}{0.8 + 0.8} = 0.8 \). |
| **ROC AUC (Receiver Operating Characteristic - Area Under Curve)** | Calculated as the area under the ROC curve, which plots True Positive Rate (TPR) vs. False Positive Rate (FPR). | If AUC = 0.95, the model has a 95% chance of ranking a positive instance higher than a negative one. |
| **Accuracy**  | \( \text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN} \) | If a model classifies 90 out of 100 test cases correctly, Accuracy = 90%. |

---

### **📌 Regression Metrics**
| **Metric Name**  | **Calculation Formula**  | **Example Understanding**  |
|------------------|-------------------------|----------------------------|
| **Mean Squared Error (MSE)**  | \( MSE = \frac{1}{n} \sum (y_{\text{true}} - y_{\text{pred}})^2 \) | If actual values are [3, 5, 2] and predicted values are [2.5, 5.5, 1.5], MSE = \( \frac{(3-2.5)^2 + (5-5.5)^2 + (2-1.5)^2}{3} \). |
| **Root Mean Squared Error (RMSE)**  | \( RMSE = \sqrt{MSE} \) | If MSE = 4, then RMSE = 2, indicating that the model’s predictions deviate by 2 on average. |
| **Mean Absolute Error (MAE)**  | \( MAE = \frac{1}{n} \sum |y_{\text{true}} - y_{\text{pred}}| \) | If actual values are [3, 5, 2] and predicted values are [2.5, 5.5, 1.5], MAE = \( \frac{|3-2.5| + |5-5.5| + |2-1.5|}{3} \). |
| **R-squared (R² Score)**  | \( R^2 = 1 - \frac{\sum (y_{\text{true}} - y_{\text{pred}})^2}{\sum (y_{\text{true}} - \bar{y})^2} \) | If \( R^2 \) is 0.9, the model explains 90% of the variance in the data. |

---

### **📌 Calibration Metrics**
| **Metric Name**  | **Calculation Formula**  | **Example Understanding**  |
|------------------|-------------------------|----------------------------|
| **Brier Score Loss**  | \( BSL = \frac{1}{n} \sum (p_{\text{pred}} - y_{\text{true}})^2 \) | If a model predicts probabilities [0.8, 0.6, 0.2] for true labels [1, 1, 0], the Brier Score measures how well these probabilities reflect reality. |
| **Log Loss (Cross-Entropy Loss)**  | \( LogLoss = -\frac{1}{n} \sum (y_{\text{true}} \log p_{\text{pred}} + (1 - y_{\text{true}}) \log(1 - p_{\text{pred}})) \) | If a model predicts 90% confidence for an event that happens, Log Loss is low; if it predicts 90% confidence and it's wrong, Log Loss is high. |
| **Calibration Curve**  | A plot comparing predicted probability vs. actual probability. | A well-calibrated model should produce a diagonal line where predicted probabilities match actual frequencies. |

---
