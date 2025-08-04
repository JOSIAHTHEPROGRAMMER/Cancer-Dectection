# Breast Cancer Prediction using Logistic Regression

This project uses a **Logistic Regression** model to predict whether a tumor is **Malignant** or **Benign** based on clinical features. The model is trained using a dataset from [Kaggle](https://www.kaggle.com/datasets/wasiqaliyasir/breast-cancer-dataset).

---

## Dataset

The dataset contains **569 entries** and **32 features**, including:
- Measurements like `radius_mean`, `texture_mean`, `perimeter_mean`, etc.
- A target column `diagnosis`:
  - `M` = Malignant
  - `B` = Benign

> Note: An unused column (`Unnamed: 32`) was removed during preprocessing.

---

## Features

- Data Cleaning and Preprocessing
- Label Encoding of Diagnosis (M = 1, B = 0)
- Feature Scaling using `StandardScaler`
- Train-Test Split
- Logistic Regression Model
- Prediction on New Input
- Custom user input support

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/breast-cancer-predictor.git
cd breast-cancer-predictor
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Notebook
Open the notebook using Jupyter, VS Code, or Colab:

```bash
CancerPrediction.ipynb

```
### Or use Kaggle Notebooks, and make sure the dataset path matches:

```python
df = pd.read_csv('/kaggle/input/breast-cancer-dataset/Breast-cancer-dataset.csv')
```

## Sample Prediction
#### You can manually test the model with new data:

```python
input_data = [
    11.5, 12.0, 75.0, 400.0, 0.09, 0.05, 0.04, 0.03, 0.15, 0.05,
    0.25, 0.6, 1.5, 15.0, 0.005, 0.01, 0.015, 0.01, 0.015, 0.002,
    13.0, 14.0, 85.0, 500.0, 0.12, 0.1, 0.09, 0.07, 0.18, 0.06
]

# Convert to DataFrame with proper column names
input_df = pd.DataFrame([input_data], columns=X.columns)
input_scaled = scaler.transform(input_df)

# Make prediction
prediction = model.predict(input_scaled)[0]
print("Prediction:", "Malignant" if prediction == 1 else "Benign")
```
### Output:
```bash
Prediction: Benign
```
#### The model outputs either Malignant or Benign based on the logistic regression result (0 or 1). It uses probability thresholds (default 0.5) to classify.
