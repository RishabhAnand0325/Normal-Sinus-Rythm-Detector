# Normal-Sinus-Rythm-Detector

# Detecting Normal Sinus Rhythm (NSR) from ECG Beats

## 1. Introduction

* **Problem Statement:** Automatically detect Normal Sinus Rhythm (NSR) vs. abnormal heartbeats using ECG data.
* **Motivation:** NSR detection helps in early identification of arrhythmias and cardiovascular disorders.
* **Dataset:** Combined MIT-BIH Arrhythmia and PTB Diagnostic datasets, pre-segmented beats of 187 samples each.
* **Goal:** Build a binary classifier achieving >85% accuracy on the test set.

---

## 2. Data Overview

* **MIT-BIH Dataset:** Annotated arrhythmia ECG beats.
* **PTB Dataset:** Normal vs. abnormal ECG segments.
* **Preprocessing:**

  * Combined both datasets.
  * Labeled as **1 = Normal (NSR)**, **0 = Abnormal**.
  * Standardized signals to zero mean and unit variance.
* **Final dataset size:** \~200k+ beats.
* **Challenge:** Class imbalance between NSR and abnormal beats.

---

## 3. Methodology

1. **Data Preparation:**

   * Train/test split (80/20), stratified by class.
   * StandardScaler applied.

2. **Modeling Approaches:**

   * **Random Forest (baseline):** Robust to noise, interpretable.
   * **Logistic Regression (benchmark):** Simple linear model.
   * **Optional Deep Learning (MLP with Keras):** Captures non-linear features.

3. **Evaluation Metrics:**

   * Accuracy, Precision, Recall, F1-score.
   * Confusion Matrix for error analysis.

---

## 4. Results

* **Random Forest Classifier:**

  * Accuracy: \~95-96%
  * Precision: \~0.87
  * Recall: \~0.89
  * F1-score: \~0.88
* **Logistic Regression:** Lower but >75% accuracy on smaller subsets.
* **Keras MLP:** Potential to reach >70% with tuned hyperparameters.

**Confusion Matrix:**

* True Positives (Correct NSR) and True Negatives (Correct Abnormal) dominate.
* Some misclassifications between borderline cases.

---

## 5. Visualization

* Example ECG beats plotted for NSR vs. abnormal.
* Confusion matrix heatmap.
* Training/validation accuracy curves for deep learning model (when used).

---

## 6. Medical Context & Limitations

* **Strengths:**

  * Automated pipeline for NSR detection.
  * Good performance (>85% accuracy).
  * Scalable to larger datasets.

* **Limitations:**

  * Dataset consists of pre-segmented beats; real-world detection requires continuous signal processing.
  * Patient-level splitting not enforced → possible data leakage.
  * Clinical validation required before deployment.

* **Ethical Considerations:**

  * Should be used as **decision support**, not replacement for cardiologists.
  * Regulatory approval required for real-world medical use.

---

## 7. Conclusions

* Successfully built an AI model detecting NSR with >85% accuracy.
* Random Forest baseline performed robustly.
* Deep learning has potential for further improvement.
* Clear path for extension with more advanced models and real-world ECG recordings.

---

## 8. Future Work

* Incorporate temporal features (R-R intervals, heart rate variability).
* Explore CNNs or Transformers on raw ECG signals.
* Apply patient-wise cross-validation to avoid overfitting.
* Validate on independent datasets.

---

## 9. Key Takeaways

* **NSR can be detected automatically with high accuracy using ML.**
* **Random Forest provides an interpretable, strong baseline.**
* **Further work is needed for clinical deployment.**
