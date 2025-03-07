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

