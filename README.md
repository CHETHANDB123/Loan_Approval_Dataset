# 🏦 Loan Approval Prediction with Explainable AI

A Machine Learning project that predicts loan approval decisions and uses a **Large Language Model (Gemini)** to explain the result in plain English — making it an **Explainable AI (XAI)** system.

---

## 📌 Problem Statement

Banks receive thousands of loan applications every day. Manually reviewing each one is slow and inconsistent. This project builds an ML model that **automatically predicts whether a loan should be approved or rejected** based on applicant details — and then uses an LLM to **explain why** in simple language that any applicant can understand.

---

## 📂 Dataset

- **File:** `train_u6lujuX_CVtuZ9i.csv`
- **Type:** Classification (Approved / Rejected)
- **Features (11):**

| Feature | Description |
|---|---|
| `Gender` | Male / Female |
| `Married` | Yes / No |
| `Dependents` | Number of dependents (0, 1, 2, 3+) |
| `Education` | Graduate / Not Graduate |
| `Self_Employed` | Yes / No |
| `ApplicantIncome` | Applicant's monthly income |
| `CoapplicantIncome` | Co-applicant's monthly income |
| `LoanAmount` | Loan amount requested |
| `Loan_Amount_Term` | Loan term in months |
| `Credit_History` | Credit history (1 = good, 0 = bad) |
| `Property_Area` | Urban / Semiurban / Rural |

- **Target:** `Loan_Status` → Y = Approved, N = Rejected

---

## 🤖 ML Models Used

| Model | Type |
|---|---|
| Linear Regression | Baseline (regression-based) |
| K-Nearest Neighbors (KNN) | Classification |
| Decision Tree | Classification |
| **Random Forest** | ✅ Best model used for deployment |
| XGBoost | Boosting |

---

## 🧠 LLM Integration (Gemini)

After the Random Forest model predicts the loan decision, **Google Gemini (LLM)** generates a plain-English explanation for the applicant — this technique is called **Explainable AI (XAI)**.

**Example output:**
> "Your loan was rejected primarily due to a low credit history score and high loan amount relative to your income. To improve your chances, consider improving your credit score by clearing existing dues and applying for a smaller loan amount."

---

## 🛠️ Technologies Used

- **Language:** Python 3
- **Platform:** Google Colab
- **ML Libraries:** Pandas, NumPy, Scikit-learn
- **Encoding:** LabelEncoder, OneHotEncoder, Dummy Variables
- **Scaling:** MinMaxScaler, StandardScaler
- **Visualization:** Matplotlib, Seaborn
- **LLM:** Google Gemini API (`google-genai`)
- **UI:** Gradio

---

## 📊 Data Preprocessing Steps

1. Loaded dataset and explored with `head()`, `info()`, `describe()`
2. Filled null values — mean (LoanAmount), mode (Gender, Married, Dependents, Self_Employed), fixed value 360 (Loan_Amount_Term)
3. Dropped remaining null rows
4. Replaced `3+` in Dependents with `3`
5. Converted `Loan_Status` Y→1, N→0
6. Label encoded categorical columns (`Gender`, `Married`, `Education`, `Self_Employed`, `Property_Area`)
7. Applied MinMaxScaler and StandardScaler for numerical features
8. Correlation analysis using heatmap

---

## 📈 Data Visualizations

1. Correlation Heatmap
2. Multivariate Pairplot
3. Box Plot — Applicant Income vs Loan Status
4. Count Plot — Loan Approval Distribution
5. Bar Plot — Property Area vs Loan Status
6. Histogram — Loan Amount Distribution
7. Count Plot — Credit History vs Loan Approval

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/CHETHANDB123/Loan_Approval_Dataset.git
```

### 2. Open in Google Colab
Upload `Loan_Approval_Dataset.ipynb` to [colab.research.google.com](https://colab.research.google.com)

### 3. Upload the dataset
Upload `train_u6lujuX_CVtuZ9i.csv` to `/content/` in Colab

### 4. Add your Gemini API key
- Go to [aistudio.google.com](https://aistudio.google.com) → Get API key (free)
- In Colab, click the 🔑 key icon → Add secret named `LoanData` → paste your key
- Toggle **Notebook access ON**

### 5. Run all cells
Run all cells from top to bottom. The Gradio UI will launch automatically.

### 6. Use the app
Fill in the loan details → Click **Check Eligibility** → See the decision + AI explanation

---

## 🎯 Results

| Model | Accuracy |
|---|---|
| Linear Regression | ~71% |
| KNN (k=11) | ~75% |
| Decision Tree | ~73% |
| **Random Forest** | **~78%** |
| XGBoost | ~77% |

> Random Forest was selected as the final model for deployment due to highest accuracy.

---

## 💡 What is Explainable AI (XAI)?

Most ML models are "black boxes" — they give a result but don't explain why. This project adds an **LLM explanation layer** using Google Gemini that converts the model's binary decision into a human-readable reason. This is a real technique used in banking and finance to comply with regulations requiring transparent AI decisions.

---

## 📁 Project Structure

```
Loan_Approval_Dataset/
│
├── Loan_Approval_Dataset.ipynb      ← Main notebook
├── train_u6lujuX_CVtuZ9i.csv       ← Dataset
└── README.md                        ← This file
```

---

## 👨‍💻 Author

Made with ❤️ using Python, Scikit-learn, and Google Gemini

**CHETHANDB123**
🔗 [github.com/CHETHANDB123/Loan_Approval_Dataset](https://github.com/CHETHANDB123/Loan_Approval_Dataset)

---

> 🚀 **Machine Learning + LLM Project**
> Built a Loan Approval prediction system using Random Forest + Gemini AI for explainability.
> 🔹 Best Accuracy: ~78% (Random Forest) 🔹 LLM: Google Gemini 2.5 Flash
> 🔹 Features: Data preprocessing, 5 ML models, 7 visualizations, Explainable AI
> Open to feedback and suggestions!
