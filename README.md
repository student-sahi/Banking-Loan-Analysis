# 🏦 Banking Loan Analysis

An exploratory data analysis (EDA) project in Python that evaluates a bank's loan portfolio. It computes key lending KPIs, separates good loans from bad loans, and visualises monthly trends and funding distribution across states, loan terms, employment length, loan purpose and home ownership.


## 📌 Table of Contents

- Project Overview
- Objectives
- Dataset
- Tech Stack
- Key Metrics and Results
- Visualisations
- Project Structure
- Getting Started
- Methodology
- Future Improvements
- Author

---

## 📖 Project Overview

Lending institutions need a clear view of how much they lend, how much they recover, and how risky their portfolio is. This project analyses a dataset of **38,576 loan applications** issued in 2021 to answer those questions. The analysis is split into two parts:

1. **KPI Analysis**: portfolio-level and month-to-date (MTD) metrics, plus a good vs. bad loan comparison.
2. **Visual Analysis**: monthly trends and breakdowns of funded amount by key borrower and loan attributes.

## 🎯 Objectives

- Measure total loan applications, funded amount and amount received.
- Track month-to-date (MTD) performance for the latest month in the data.
- Calculate the average interest rate and average debt-to-income (DTI) ratio.
- Classify loans as **good** (`Fully Paid`, `Current`) or **bad** (all other statuses) and compare them.
- Identify trends over time and the segments that drive lending volume.

## 📂 Dataset

**File:** `financial_loan.xlsx` (38,576 rows, 24 columns)

| Column | Description |
|---|---|
| `id`, `member_id` | Unique loan and borrower identifiers |
| `address_state` | State of the borrower |
| `application_type` | Individual or joint application |
| `emp_length`, `emp_title` | Employment length and employer |
| `grade`, `sub_grade` | Loan risk grade assigned to the borrower |
| `home_ownership` | Rent, Mortgage, Own, etc. |
| `issue_date`, `last_credit_pull_date`, `last_payment_date`, `next_payment_date` | Loan lifecycle dates |
| `loan_status` | Fully Paid, Current, Charged Off, etc. |
| `purpose` | Reason for the loan |
| `term` | 36 or 60 months |
| `verification_status` | Income verification status |
| `annual_income`, `dti` | Borrower income and debt-to-income ratio |
| `installment`, `int_rate` | Monthly instalment and interest rate |
| `loan_amount`, `total_payment`, `total_acc` | Funded amount, amount received, total credit accounts |

> **Note:** The dataset is not included in this repository. Place `financial_loan.xlsx` in the project root before running the notebook.

## 🛠 Tech Stack

- **Language:** Python 3
- **Libraries:** pandas, NumPy, Matplotlib, Seaborn
- **Excel reader:** openpyxl (required by `pandas.read_excel`)
- **Environment:** Jupyter Notebook

## 📊 Key Metrics and Results

### Portfolio KPIs

| KPI | Value |
|---|---|
| Total Loan Applications | **38,576** |
| MTD Loan Applications (Dec 2021) | **4,314** |
| Total Funded Amount | **435.76 M** |
| MTD Funded Amount (Dec 2021) | **53.98 M** |
| Total Amount Received | **473.07 M** |
| Average Interest Rate | **12.05%** |
| Average DTI | **13.33%** |

### Good Loan vs. Bad Loan

| Metric | Good Loans | Bad Loans |
|---|---|---|
| Applications | 33,243 | 5,333 |
| Share of Portfolio | **86.18%** | **13.82%** |
| Funded Amount | 370.22 M | 65.53 M |
| Amount Received | 435.79 M | 37.28 M |

> **Definitions:** *Good loans* have status `Fully Paid` or `Current`. *Bad loans* are every other status (e.g. Charged Off).

## 📈 Visualisations

The notebook generates the following charts:

| # | Chart | Type |
|---|---|---|
| 1 | Total Funded Amount by Month | Area / line chart |
| 2 | Total Received Amount by Month | Area / line chart |
| 3 | Total Loan Applications by Month | Area / line chart |
| 4 | Top 15 States by Funded Amount | Horizontal bar chart |
| 5 | Funded Amount by Loan Term | Donut chart |
| 6 | Funded Amount by Employment Length | Horizontal bar chart |
| 7 | Funded Amount by Loan Purpose | Horizontal bar chart |
| 8 | Funded Amount by Home Ownership | Horizontal bar chart |

> 💡 Tip: Save the charts into an `images/` folder and embed them here, e.g. `![Monthly Funded Amount](images/monthly_funded.png)`.

## 📁 Project Structure

```
Banking-Loan-Analysis/
│
├── Banking_Loan_Analysis_.ipynb   # Main analysis notebook
├── financial_loan.xlsx            # Dataset (add locally)
├── requirements.txt               # Python dependencies
└── README.md                      # Project documentation
```

## 🚀 Getting Started

### Prerequisites

- Python 3.9 or higher
- Jupyter Notebook or JupyterLab

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/Banking-Loan-Analysis.git
cd Banking-Loan-Analysis

# 2. (Optional) Create a virtual environment
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# 3. Install dependencies
pip install numpy pandas matplotlib seaborn openpyxl jupyter
```

### Run the Notebook

```bash
jupyter notebook Banking_Loan_Analysis_.ipynb
```

Then run all cells (**Kernel → Restart & Run All**).

## 🔬 Methodology

1. **Data loading:** read `financial_loan.xlsx` into a pandas DataFrame and inspect it with `head()`, `tail()` and `dtypes`.
2. **KPI calculation:** aggregate application counts, funded amounts and payments. The MTD figures use the latest `issue_date` in the data to define the current month.
3. **Loan classification:** split the portfolio into good and bad loans based on `loan_status` and compare their counts, funded amounts and recoveries.
4. **Trend analysis:** group by month of `issue_date` and plot funded amount, received amount and application volume.
5. **Segment analysis:** group funded amount by state, term, employment length, purpose and home ownership.

## 🔮 Future Improvements

- Add a loan default prediction model (e.g. Logistic Regression, Random Forest).
- Analyse risk by `grade` and `sub_grade`.
- Build an interactive dashboard in Power BI, Tableau or Streamlit.
- Add statistical tests and correlation analysis (income, DTI, interest rate vs. default).
- Standardise currency labelling across all charts and outputs.

## 👤 Author

**Your Name**
- GitHub: mhaskesahil
- LinkedIn: www.linkedin.com/in/sahilmhaske

---

⭐ If you found this project useful, consider giving it a star!
