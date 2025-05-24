# EHR-Heart: Heart Disease Predictor

A machine learning project comparing traditional models and transformer-based models (TabTransformer) for predicting heart disease using an Electronic Health Record (EHR) dataset.

---

## 📊 Dataset

- Dataset: [UCI Heart Disease dataset](https://archive.ics.uci.edu/ml/datasets/heart+Disease)
- File: `heart.csv`

---

## 🧠 Models Used

1. Logistic Regression
2. Random Forest
3. Support Vector Machine (SVM)
4. K-Nearest Neighbors (KNN)
5. Decision Tree
6. Naive Bayes
7. TabTransformer (via a PyTorch-based MLP as a simplified placeholder)

---

## 📁 Project Structure

- `01_data_exploration.ipynb`: Exploratory data analysis and feature correlation.
- `02_ml_models_comparison.ipynb`: Training and evaluating traditional ML models.
- `03_tabtransformer_model.py`: TabTransformer model implementation using PyTorch.

---

## 📈 Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC

---

## 📌 Conclusion

Transformer models such as TabTransformer show potential in structured EHR data. However, traditional models like Random Forest and SVM remain strong baselines in terms of interpretability and efficiency.

---

## 👨‍💻 Author

- **Febin Modavancheri**  
- MSc Data Science Dissertation Project  
- [Portfolio](https://febinmodavancheri.github.io)
