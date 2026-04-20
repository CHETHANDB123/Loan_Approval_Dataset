# 🏦 Loan Approval Prediction with Explainable AI

A Machine Learning project that predicts loan approval decisions and uses a **Large Language Model (Gemini)** to explain the result in plain English — making it an **Explainable AI (XAI)** system.

---

## 📌 Problem Statement

Banks receive thousands of loan applications every day. Manually reviewing each one is slow and inconsistent. This project builds an ML model that **automatically predicts whether a loan should be approved or rejected** based on applicant details — and then uses an LLM to **explain why** in simple language that any applicant can understand.

---

## 📂 Dataset

- **File:** `Loan_1.csv`
- **Type:** Classification (Approved / Rejected)
- **Features (11):**

| Feature | Description |
|---|---|
| `no_of_dependents` | Number of dependents |
| `education` | Graduate / Not Graduate |
| `self_employed` | Yes / No |
| `income_annum` | Annual income |
| `loan_amount` | Loan amount requested |
| `loan_term` | Loan term in months |
| `cibil_score` | Credit score |
| `residential_assets_value` | Value of residential assets |
| `commercial_assets_value` | Value of commercial assets |
| `luxury_assets_value` | Value of luxury assets |
| `bank_asset_value` | Value of bank assets |

- **Target:** `loan_status` → 0 = Approved, 1 = Rejected

---

## 🤖 ML Models Used

| Model | Type |
|---|---|
| Linear Regression | Baseline (regression-based) |
| K-Nearest Neighbors (KNN) | Classification |
| Decision Tree | Classification |
| **Random Forest** | ✅ Best model used for deployment |

---

## 🧠 LLM Integration (Gemini)

After the Random Forest model predicts the loan decision, **Google Gemini (LLM)** generates a plain-English explanation for the applicant — this technique is called **Explainable AI (XAI)**.

**Example output:**
> "Your loan was rejected primarily due to a low CIBIL score and high loan amount relative to your income. To improve your chances, consider improving your credit score by clearing existing dues and applying for a smaller loan amount."

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
2. Filled null values — mean (loan_amount), median (loan_term), mode (education, self_employed)
3. Dropped remaining null rows
4. Cleaned `no_of_dependents` column (removed `+` symbol)
5. Label encoded categorical columns (`education`, `self_employed`, `loan_status`)
6. Applied MinMaxScaler and StandardScaler for numerical features
7. Correlation analysis using heatmap

---

## 📈 Data Visualizations

1. Correlation Heatmap
2. Multivariate Pairplot
3. Box Plot — Income vs Loan Status
4. Count Plot — Loan Approval Distribution
5. Bar Plot — Residential Assets vs Loan Status
6. Histogram — Loan Amount Distribution
7. Count Plot — CIBIL Score vs Loan Status

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/loan-approval-prediction.git
```

### 2. Open in Google Colab
Upload `Loan_Approval_Prediction.ipynb` to [colab.research.google.com](https://colab.research.google.com)

### 3. Upload the dataset
Upload `Loan_1.csv` to `/content/` in Colab

### 4. Add your Gemini API key
- Go to [aistudio.google.com](https://aistudio.google.com) → Get API key (free)
- In Colab, click the 🔑 key icon → Add secret named `LoanData` → paste your key

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

> Random Forest was selected as the final model for deployment due to highest accuracy.

---

## 💡 What is Explainable AI (XAI)?

Most ML models are "black boxes" — they give a result but don't explain why. This project adds an **LLM explanation layer** using Google Gemini that converts the model's binary decision into a human-readable reason. This is a real technique used in banking and finance to comply with regulations requiring transparent AI decisions.

---

## 📁 Project Structure

```
loan-approval-prediction/
│
├── Loan_Approval_Prediction.ipynb   ← Main notebook
├── Loan_1.csv                       ← Dataset
└── README.md                        ← This file
```

---

## 👨‍💻 Author

Made with ❤️ using Python, Scikit-learn, and Google Gemini

> 🚀 **Machine Learning + LLM Project**  
> Built a Loan Approval prediction system using Random Forest + Gemini AI for explainability.  
> 🔹 Best Accuracy: ~78% (Random Forest) 🔹 LLM: Google Gemini 2.5 Flash  
> 🔹 Features: Data preprocessing, 4 ML models, 7 visualizations, Explainable AI  
> Open to feedback and suggestions!
