# 🏥 Diabetes Risk Analysis

A comprehensive, end-to-end data science project combining Exploratory Data Analysis, Machine Learning Prediction, and Patient Segmentation on a 10,000-patient clinical dataset.

---

## 📁 Dataset
- **Source:** Diabetes clinical dataset (10,000 patients, 20 features)
- **Features include:** Age, BMI, Waist Circumference, Blood Pressure, Cholesterol (Total/HDL/LDL), HbA1c, Fasting Blood Glucose, GGT, Serum Urate, Dietary Intake, and lifestyle factors (Smoking, Alcohol, Physical Activity)
- **Target variable:** `Diabetic` — derived using WHO clinical standards (HbA1c ≥ 6.5 or Fasting Blood Glucose ≥ 126)

---

## 🔧 Tools & Libraries
- Python 3.11
- Pandas, NumPy
- Seaborn, Matplotlib
- Scikit-learn (RandomForestClassifier, KMeans, StandardScaler)

---

## 📌 Project Structure

This project combines 3 data science techniques in one notebook:

### Part 1 — Exploratory Data Analysis (EDA)
- Distribution of Age and BMI by diabetic status
- Clinical markers comparison (HbA1c, Fasting Glucose, Waist Circumference)
- Lifestyle factors vs diabetes rate (Smoking, Alcohol, Physical Activity)
- Full correlation heatmap across all 13 numeric features

### Part 2 — Diabetes Risk Prediction
- Random Forest Classifier with 100 estimators
- Identified and fixed **data leakage** (HbA1c and Fasting Glucose defined the target)
- Handled **class imbalance** (90.5% diabetic) using downsampling
- Feature importance analysis of lifestyle and demographic predictors

### Part 3 — Patient Segmentation (K-Means Clustering)
- Elbow method to find optimal number of clusters
- 4 distinct patient profiles identified
- Cluster profiling by Age, BMI, Cholesterol, and Blood Pressure

---

## 📈 Key Findings

### EDA
- **HbA1c** and **Fasting Blood Glucose** are the strongest predictors of diabetes (correlations: 0.44 and 0.32)
- Lifestyle factors alone (smoking, alcohol, activity level) show no meaningful differentiation between diabetic and non-diabetic patients
- BMI and Age are evenly distributed across both groups in this dataset

### Prediction Model
- Without clinical blood markers, lifestyle features alone yield ~47% accuracy
- This is **medically accurate** — diabetes cannot be reliably diagnosed without blood tests
- Key lesson learned: **data leakage** can produce misleadingly perfect 100% accuracy

### Patient Clusters
| Cluster | Age | BMI | Cholesterol | HDL | Profile |
|---------|-----|-----|-------------|-----|---------|
| 0 | 55.7 | 30.1 | 194.6 | 45.1 | Older, elevated BP, low HDL — hypertension risk |
| 1 | 34.3 | 28.4 | 191.1 | 64.4 | Young, healthy cholesterol profile |
| 2 | 52.8 | 30.5 | 256.7 | 66.7 | Middle-aged, high cholesterol, good HDL |
| 3 | 35.6 | 28.6 | 257.1 | 43.7 | Young, high cholesterol, low HDL — cardiovascular risk |

---

## 💡 Clinical Recommendations
1. **Routine blood tests are essential** — HbA1c and fasting glucose are irreplaceable for diabetes screening
2. **Target Clusters 0 and 3** for early lifestyle interventions — both show elevated cardiovascular risk markers
3. **Young high-cholesterol patients** (Cluster 3) need early monitoring despite their age
4. Lifestyle modifications alone are insufficient without clinical monitoring

---

## 🧠 Concepts Demonstrated
- Exploratory Data Analysis (EDA)
- Handling missing values and class imbalance
- Detecting and fixing data leakage
- Supervised ML — Random Forest Classifier
- Unsupervised ML — K-Means Clustering with Elbow Method
- Feature importance analysis
- Clinical data interpretation

---

## 📂 Files
- `diabetes_analysis.ipynb` — full annotated analysis notebook
- `diabetes_dataset.csv` — patient dataset (include in same folder to run)
