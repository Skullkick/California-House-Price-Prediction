## 🏠 **California House Price Prediction Project — Summary**

### 🎯 **Project Objective:**

To **predict median house values** in California using the **Kaggle housing dataset**, applying machine learning techniques through a full data science workflow: exploration, preprocessing, feature engineering, modeling, and evaluation.

---

## 📊 **Key Workflow Steps:**

### 1. **Data Exploration:**

* **Dataset:** Includes location (latitude, longitude), housing features, population, income, and proximity to ocean.
* **Target Variable:** `median_house_value`
* **Insights:**

  * `median_income` has strong positive correlation with house prices.
  * Coastal proximity strongly influences prices.
  * Features like `total_rooms`, `population`, etc., are skewed and need transformation.

---

### 2. **Data Preprocessing:**

* **Missing Values:** `total_bedrooms` entries with missing data were dropped.
* **Log Transformations:** Applied on skewed numerical features using `np.log(value + 1)`.
* **Categorical Encoding:** `ocean_proximity` one-hot encoded.
* **Feature Scaling:** StandardScaler applied (important for some models).
* **Train-Test Split:** 80-20 split using `train_test_split`.

---

### 3. **Feature Engineering:**

* **New Features:**

  * `bedroom_ratio = total_bedrooms / total_rooms`
  * `household_rooms = total_rooms / households`
* These features provided additional correlation with the target.

---

### 4. **Modeling and Results:**

| Model                  | Score on Test Data |
| ---------------------- | ------------------ |
| **Linear Regression**  | **0.6711**         |
| **Random Forest**      | **0.8156**         |
| **GridSearchCV Tuned** | **0.8127**         |

* **Linear Regression:** A decent baseline model.
* **Random Forest Regressor:** Outperformed linear regression significantly.
* **Hyperparameter Tuning (GridSearchCV):**

  * Did not improve performance over default parameters.
  * Indicates defaults may already be near-optimal or tuning grid was suboptimal.

---

### ⚙️ **Libraries Used:**

* `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

---

## 📌 **Insights & Learnings:**

* **Data preprocessing and feature engineering** significantly affect model performance.
* **Random Forest** is robust and performs well even without tuning.
* **Hyperparameter tuning** doesn't always guarantee improvement; it depends on the grid and data.

---

## ✅ **Conclusion:**

The project showcases a **complete regression pipeline**. While **Linear Regression** gives a starting point, **Random Forest** clearly performs better. However, default Random Forest parameters turned out to be more effective than the tuned ones in this case, highlighting the importance of smart tuning strategies.

