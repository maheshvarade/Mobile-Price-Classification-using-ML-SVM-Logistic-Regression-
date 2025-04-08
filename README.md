# Mobile-Price-Classification-using-ML-SVM-Logistic-Regression-

This project tackles the challenge faced by a new mobile company founded by *Prabhat*, who wants to compete with tech giants like Apple and Samsung. The goal is to **predict the price range** of a mobile phone based on its features — not the exact price, but whether it's **low, medium, high, or very high** cost.

---

## 📊 About the Dataset

The dataset contains **2000 mobile phone records** with **21 features**, both numerical and categorical.

### 🔍 Key Features:

- `battery_power`: Total energy the battery can store (mAh)
- `ram`: RAM (MB)
- `int_memory`: Internal memory (GB)
- `px_height` / `px_width`: Screen resolution
- `mobile_wt`: Mobile weight
- `fc` / `pc`: Front and Primary Camera (MP)
- `price_range`: **Target** (0 = low, 1 = medium, 2 = high, 3 = very high)

📌 **Note**: `fc` column shows outliers in a box plot, but we chose not to remove them, as they don't significantly hurt model performance.

---

## 🧠 Problem Statement

Help Prabhat estimate a **price range** for his new mobile devices based on their specifications using Machine Learning. Since he’s not proficient in ML, we step in to:

- Build a classification model
- Compare performance with and without feature scaling
- Demonstrate the importance of scaling for certain algorithms

---

## 🛠️ Machine Learning Approach

We experimented with two main classifiers:

### ✅ 1. Support Vector Machine (SVM)

- **No Scaling**
- Achieved **high accuracy** on the raw dataset
- 📈 **Test Accuracy**: `94%`

**Classification Report (Unscaled Data):**
       0       0.99      0.97      0.98
       1       0.95      0.92      0.93
       2       0.91      0.91      0.91
       3       0.93      0.97      0.95

---

### ✅ 2. Logistic Regression

- **Performed poorly without scaling**
- After applying **Standard Scaling to selected columns**:
  - `battery_power`, `int_memory`, `mobile_wt`, `px_height`, `px_width`, `ram`
- Significant performance improvement!

**Classification Report (After Scaling):**
       0       0.95      0.97      0.96
       1       0.92      0.91      0.91
       2       0.91      0.91      0.91
       3       0.95      0.94      0.95
       
📈 **Improved Accuracy**: `93%`  
📌 Scaling made a **big difference** for Logistic Regression, confirming its sensitivity to feature magnitudes.

---

## ⚙️ Preprocessing Summary

- Feature selection
- Outlier analysis (no removal)
- StandardScaler applied **only to selected numerical columns**
- Target: `price_range` (multiclass classification)

---

## 💡 Key Takeaways

- **SVM performs well without scaling**, especially on this dataset
- **Logistic Regression requires scaling** to reach comparable accuracy
- **RAM is highly correlated with price** — one of the most predictive features
- Proper preprocessing = major impact on model performance


---

## ✅ Future Improvements

- Add more models (Random Forest, XGBoost, etc.)
- Hyperparameter tuning
- Cross-validation
- Deployment via Streamlit or Flask

---

## 🤝 Let's Collaborate

Feel free to fork this repo, submit issues, or suggest improvements. Whether you're learning ML or just interested in mobile pricing strategies, let's learn together!

---






