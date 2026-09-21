# 📊 Financial Consumer Complaints Analysis 📉

> _Analyzing 62,516 CFPB financial consumer complaints to uncover trends, product risk patterns, and company response effectiveness using Python and Power BI._

---

## 📋 Table of Contents

- <a href="#overview">Overview</a>
- <a href="#business-problem">Business Problem</a>
- <a href="#dataset">Dataset</a>
- <a href="#tools--technologies">Tools & Technologies</a>
- <a href="#project-structure">Project Structure</a>
- <a href="#data-cleaning--preparation">Data Cleaning & Preparation</a>
- <a href="#exploratory-data-analysis-eda">Exploratory Data Analysis (EDA)</a>
- <a href="#dashboard">Dashboard</a>
- <a href="#key-findings">Key Findings</a>
- <a href="#business-recommendations">Business Recommendations</a>
- <a href="#how-to-run-this-project">How to Run This Project</a>
- <a href="#author--contact">Author & Contact</a>

---

<h2><a class="anchor" id="overview"></a>Overview</h2>

This project analyzes **62,516 real-world CFPB financial consumer complaints** 
from 2017–2023 to understand complaint trends, identify high-risk products, 
and evaluate company response effectiveness.

A complete data pipeline was built using **Python** for data cleaning and EDA, 
and **Power BI** for interactive dashboard visualization with DAX measures.

---

<h2><a class="anchor" id="business-problem"></a>Business Problem</h2>

Financial institutions receive thousands of consumer complaints every year.
This project aims to:

- Identify which products generate the most complaints
- Analyze company response effectiveness and timelines
- Uncover geographic complaint patterns across US states
- Track complaint growth trends over 5+ years
- Provide actionable business recommendations

---

<h2><a class="anchor" id="dataset"></a>Dataset</h2>

**Source:** [Maven Analytics](https://www.mavenanalytics.io)

| Table | Rows | Columns | Description |
|-------|------|---------|-------------|
| `Consumer_Complaints` | 62,516 | 12 | Consumer complaints, products, responses & dates |

**Key Columns:**
- Product — Type of financial product complained about
- Issue — Nature of the complaint
- Company response — How company resolved the complaint
- Timely response — Whether response was on time
- Date submitted — When complaint was filed
- State — Geographic location of consumer

---

<h2><a class="anchor" id="tools--technologies"></a>Tools & Technologies</h2>

| Tool | Purpose |
|------|---------|
| ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) | Data Cleaning, EDA, Feature Engineering |
| ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white) | Data Manipulation |
| ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat&logo=python&logoColor=white) | Data Visualization |
| ![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=flat&logo=python&logoColor=white) | Statistical Visualization |
| ![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=flat&logo=powerbi&logoColor=black) | Interactive Dashboard & DAX Measures |

---

<h2><a class="anchor" id="project-structure"></a>Project Structure</h2>

```
financial-consumer-complaints-analysis/
│
├── 📂 data/
│   └── Consumer_Complaints.xlsx
│
├── 📂 notebook/
│   └── Financial_Complaints_EDA.ipynb
│
├── 📂 dashboard/
│   └── Financial_Complaints.pbix
│
├── 📂 images/
│   └── dashboard_preview.png
│
└── 📄 README.md
```

---

<h2><a class="anchor" id="data-cleaning--preparation"></a>Data Cleaning & Preparation</h2>

### Missing Values Handled:

| Column | Missing Count | Treatment |
|--------|--------------|-----------|
| Sub-issue | 10,858 (17.3%) | Filled with "Not Specified" |
| Sub-product | 7 (0.01%) | Filled with "Not Specified" |
| Company public response | 2,175 (3.4%) | Filled with "No Public Response" |
| Timely response? | 1,494 (2.3%) | Filled with "Unknown" |

### Feature Engineering — 6 New Features Created:

| Feature | Description |
|---------|-------------|
| `Year` | Extracted year from Date submitted |
| `Month` | Extracted month number |
| `Month_Name` | Extracted month name (Jan, Feb...) |
| `Day_of_Week` | Day complaint was submitted |
| `Quarter` | Q1, Q2, Q3, Q4 |
| `Response_Days` | Days between submission and receipt |

---

<h2><a class="anchor" id="exploratory-data-analysis-eda"></a>Exploratory Data Analysis (EDA)</h2>

### Key EDA Findings:

**Product Analysis:**
- Checking/Savings accounts = 39.7% of all complaints
- Top 2 products drive 65.6% of total complaints
- Student Loans have slowest avg response (2.1 days)

**Time Trends:**
- Complaints grew 140% over 5 years (2017–2022)
- July has highest monthly complaints (6,474)
- Weekdays receive 6.9x more complaints than weekends

**Response Analysis:**
- 93.8% complaints received timely response
- 79.4% complaints processed same day
- 2,443 complaints took 7+ days to resolve

---

<h2><a class="anchor" id="dashboard"></a>Dashboard</h2>

### Dashboard Preview
![Dashboard Preview](images/dashboard_preview.png)

### Dashboard Features:
- ✅ 7 DAX Measures
- ✅ KPI Cards (Multi-row)
- ✅ Funnel Chart — Resolution pipeline
- ✅ Scatter Plot — Response time vs Complaints
- ✅ Conditional Matrix — Product × Response
- ✅ Donut Chart — Response breakdown
- ✅ Year & Product Slicers
- ✅ Reset Bookmark Button

---

<h2><a class="anchor" id="key-findings"></a>Key Findings</h2>

| # | Finding |
|---|---------|
| 📈 | **140% Growth** — Complaints grew from 5,394 (2017) to 12,953 (2022) |
| 🏦 | **65.6% from 2 Products** — Checking/Savings & Credit Card dominate |
| 💰 | **$1 in 4 Got Relief** — 23.5% consumers received monetary compensation |
| ⚡ | **93.8% Timely Response** — Most complaints resolved on time |
| 📍 | **California Leads** — 21.9% of all complaints from CA |
| 🐢 | **Student Loans Slowest** — Avg response time 2.1 days |

---

<h2><a class="anchor" id="business-recommendations"></a>Business Recommendations</h2>

| Priority | Recommendation | Impact |
|----------|---------------|--------|
| 🔴 High | Investigate Checking/Savings process gaps | Reduce 39.7% complaints |
| 🔴 High | Root cause analysis for 2022 complaint spike | Prevent future surges |
| 🟡 Medium | Reduce 7+ day response time for slow cases | Improve 2,443 cases |
| 🟡 Medium | Weekend staffing to process complaint backlogs | Improve efficiency |

---

<h2><a class="anchor" id="how-to-run-this-project"></a>How to Run This Project</h2>

### 1. Clone Repository
```bash
git clone https://github.com/yourusername/financial-consumer-complaints-analysis.git
cd financial-consumer-complaints-analysis
```

### 2. Install Libraries
```bash
pip install pandas numpy matplotlib seaborn openpyxl jupyter
```

### 3. Run Jupyter Notebook
```bash
jupyter notebook notebook/Financial_Complaints_EDA.ipynb
```

### 4. Open Power BI Dashboard
```
Open dashboard/Financial_Complaints.pbix
in Power BI Desktop
```

---

<h2><a class="anchor" id="author--contact"></a>Author & Contact</h2>

**Your Name**  
Data Analyst | Python • Power BI • DAX • SQL

| Platform | Link |
|----------|------|
| 💼 LinkedIn | [linkedin.com/in/yourprofile](https://linkedin.com/in/yourprofile) |
| 🐙 GitHub | [github.com/yourusername](https://github.com/yourusername) |
| 📧 Email | youremail@gmail.com |

---

> _"Data is not just numbers — it tells a story.
> This project is my attempt to listen to that story
> and turn it into actionable insights."_ 💡

---

⭐ **If you found this project helpful, please give it a star!** ⭐
