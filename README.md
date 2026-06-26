# House-Price-Predictor-Linear-Regression

# 🏠 House Price Prediction using Linear Regression

A machine learning project that predicts house sale prices based on key property features using **Linear Regression**, built on the classic Ames Housing dataset.

---

## 📌 Project Overview

This project applies **supervised machine learning** (Linear Regression) on the Ames Housing dataset (`train.csv`) to predict house prices. Given a house's living area, number of bedrooms, and bathrooms, the model estimates its sale price — useful for real estate valuation and market analysis.

---

## 📂 Dataset

- **File:** `train.csv`
- **Total Records:** 1,460 houses
- **Total Features:** 81 columns
- **Features Used:**

| Feature | Description |
|---|---|
| `GrLivArea` | Above grade (ground) living area in square feet |
| `BedroomAbvGr` | Number of bedrooms above grade |
| `FullBath` | Number of full bathrooms above grade |
| `SalePrice` | Target variable — house sale price in USD |

---

## 🔧 Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data loading and manipulation |
| NumPy | Numerical operations |
| Scikit-learn | Linear Regression, train-test split, metrics |
| Matplotlib | Data visualization |
| Google Colab | Development environment |

---

## 🚀 Workflow

### 1. Data Loading & Exploration
- Loaded `train.csv` using Pandas
- Inspected shape (1,460 rows × 81 columns) and column names

### 2. Column Verification
- Verified that the required columns (`GrLivArea`, `BedroomAbvGr`, `FullBath`, `SalePrice`) exist in the dataset

### 3. Feature Selection & Preprocessing
- Selected the 4 relevant columns
- Dropped rows with missing values using `.dropna()`

### 4. Feature & Target Split
- `X` (features): `GrLivArea`, `BedroomAbvGr`, `FullBath` — shape (1460, 3)
- `y` (target): `SalePrice` — shape (1460,)

### 5. Train-Test Split
- Split data with an 80/20 ratio (`test_size=0.2`, `random_state=42`)
- Training rows: **1,168** | Testing rows: **292**

### 6. Model Training
- Trained a **Linear Regression** model on the training set

```
Coefficients:
  GrLivArea      →  104.03
  BedroomAbvGr   → -26655.17
  FullBath       →  30014.32

Intercept: 52261.75
```

### 7. Evaluation & Prediction
- Generated predictions on the test set
- Evaluated model performance using R² Score and RMSE

### 8. Visualization
- Plotted **Actual Price vs. Predicted Price** scatter chart (`result.png`)

---

## 📊 Model Performance

| Metric | Value |
|---|---|
| **R² Score** | 0.634 |
| **RMSE** | $52,975.72 |

> The model explains ~63% of the variance in house prices using just 3 features.

---

## 🎯 Sample Prediction

| GrLivArea (sqft) | Bedrooms | Full Baths | Predicted Price |
|---|---|---|---|
| 1,500 | 3 | 2 | **$188,364** |

---

## 📁 Project Structure

```
house-price-prediction/
│
├── train.csv                        # Ames Housing dataset
├── house_price_prediction.ipynb     # Main Colab notebook
├── result.png                       # Actual vs Predicted price scatter plot
└── README.md                        # Project documentation
```

---

## ▶️ How to Run

1. **Clone or download** this repository
2. Upload `train.csv` when prompted in Google Colab
3. Run all cells sequentially in `house_price_prediction.ipynb`
4. View the generated scatter plot `result.png`

**Or run locally:**
```bash
pip install numpy pandas matplotlib scikit-learn
jupyter notebook house_price_prediction.ipynb
```

---

## 💡 Key Insights

- **Living area (`GrLivArea`)** has the strongest positive impact on price — each additional square foot adds ~$104 to the predicted price.
- **Full bathrooms** contribute positively (~$30,014 per bathroom).
- **Bedrooms above grade** show a negative coefficient (~-$26,655), which is counterintuitive but common in linear models when correlated with living area (larger homes with more rooms may have smaller individual rooms).
- Using only 3 features, the model achieves a reasonable R² of 0.63 — adding more features from the full 81-column dataset could significantly improve accuracy.

---

## 🔮 Possible Improvements

- Include more features (e.g., `LotArea`, `OverallQual`, `YearBuilt`, `GarageArea`)
- Try polynomial regression or tree-based models (Random Forest, XGBoost)
- Apply feature engineering and outlier removal
- Use cross-validation for more robust evaluation

---

## 👨‍💻 Author

**Shubham Kumar Jha**  
B.Tech CSE (2025-29) | BIT Sindri
Machine Learning Intern at SkillCraft Technology

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
