# 📊 AI Dashboard Validator

## Project Overview

The **AI Dashboard Validator** is a Streamlit-based application designed to enhance the reliability and integrity of Business Intelligence (BI) dashboards. It automates the process of cross-verifying dashboard metrics against raw data and leverages Google's Gemini AI to provide intelligent insights, identify potential data discrepancies, and offer recommendations for improved visualizations and Key Performance Indicators (KPIs).

This tool helps data analysts, BI developers, and data consumers ensure that their dashboards are not only visually appealing but also accurate and convey trustworthy insights.

---

## ✅ Features

- **Dashboard & Raw Data Upload**
  - Upload dashboard JSON exports or screenshots (PNG, JPG).
  - Upload raw transactional data in CSV format.

- **Metric Validation**
  - Compare key dashboard metrics against raw data calculations.
  - Flag mismatches based on a user-defined tolerance slider.

- **Visual Integrity Audit**
  - Analyze textual context of dashboard visuals.
  - Detect issues like truncated axes, over-cluttered pie charts, etc.

- **KPI & Chart Recommendations**
  - Suggest better KPIs or chart types based on raw data.

- **AI-Powered Summary (Gemini)**
  - Generate holistic explanations from validation results.
  - Summarize findings in clean, human-readable format.

- **Export Reports**
  - Download results as **JSON** and **Markdown**.

- **Modern UI**
  - Tab-based navigation and dark theme.
  - Interactive expanders, sliders, and intelligent layout.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.9+ (Python 3.13 tested)
- [Google Gemini API Key](https://ai.google.dev/)

---

### 🛠 Installation

```bash
# Create your folder
mkdir ai-dashboard-validator
cd ai-dashboard-validator
````

**1. Create virtual environment**

```bash
python -m venv venv
```

**2. Activate it**

* Windows:

  ```bash
  .\venv\Scripts\activate
  ```
* macOS/Linux:

  ```bash
  source venv/bin/activate
  ```

**3. Create `requirements.txt`**

```txt
streamlit==1.36.0
pandas==2.2.2
google-generativeai==0.6.0
python-dotenv==1.0.1
Pillow==10.4.0
numpy==1.26.4
# Optional:
# pytesseract==0.3.10
```

**4. Install dependencies**

```bash
pip install -r requirements.txt
```

---

### 🔑 Set Gemini API Key

Create `.env` in your root directory:

```env
GEMINI_API_KEY=your_gemini_api_key_here
```

Alternatively, paste the key into the Streamlit sidebar when the app runs.

---

### 🎨 Create `styling.py`

```python
# styling.py
import streamlit as st

def inject_custom_css():
    st.markdown("""
    <style>
        .stApp {
            background-color: #0e1117;
            color: #ffffff;
        }
        .stSidebar { background-color: #1a1e24; color: white; }
        .stButton>button {
            background-color: #2563eb;
            color: white;
            border-radius: 0.5rem;
        }
        .stButton>button:hover {
            background-color: #1a56cc;
        }
        .llm-insight-box {
            background-color: #1c1f26;
            border-left: 5px solid #9333ea;
            padding: 1rem 1.5rem;
            border-radius: 0.5rem;
            color: #ffffff;
        }
    </style>
    """, unsafe_allow_html=True)
```

---

### 📁 Folder Structure

```
ai-dashboard-validator/
├── app.py
├── utils.py
├── ai_logic.py
├── validator.py
├── kpi_recommender.py
├── styling.py
├── .env
├── requirements.txt
└── .streamlit/
    └── config.toml
```

Optional `.streamlit/config.toml`:

```toml
[theme]
base = "dark"
primaryColor = "#2563eb"
backgroundColor = "#0e1117"
secondaryBackgroundColor = "#1c1f26"
textColor = "#ffffff"
```

---

## ▶️ Run the App

```bash
streamlit run app.py
```

---

## 🧠 How to Use

### Tab 1: Upload & Setup

* Upload a **dashboard** (JSON or Screenshot).
* Upload **raw CSV** file.
* Set tolerance for metric comparison.
* Click **"Start Validation"**.

### Tab 2: Validation & Insights

* View metric mismatches.
* Review visual audit issues.
* See suggested KPIs or charts.
* Read Gemini-powered AI summary.

### Tab 3: Export

* Download **JSON** or **Markdown** report.

---

## 📂 Sample Files

### `sample_dashboard_data.json`

```json
{
  "dashboardName": "Sales Overview",
  "kpis": [
    { "name": "Total Sales", "value": 100000.0 },
    { "name": "Total Orders", "value": 500 }
  ],
  "visuals": [
    {
      "title": "Sales Trend",
      "type": "Line Chart",
      "description": "Shows monthly sales with a truncated y-axis.",
      "y_axis_starts_at_zero": false
    }
  ]
}
```

### `sample_raw_data.csv`

```csv
Order_ID,Customer_ID,Product,Sales
1,A001,Laptop,1200
2,A002,Mouse,25
3,A001,Keyboard,75
...
```

---

## 🧭 Roadmap

* ✅ OCR Integration (`pytesseract`)
* ✅ Vision LLM (Gemini Pro Vision)
* ✅ Auto KPI Extractor from screenshot
* ✅ Streamlit Cloud Deployment
* ✅ GPT-4 vs Gemini explainability toggle

---

## 📄 License

This project is licensed under the **MIT License**.

---

## 🤝 Contributing

Open to ideas, feedback, or pull requests.

---

> Built with ❤️ using Streamlit + Gemini API.

```
