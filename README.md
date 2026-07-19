# 🚌 Predictive Delay & Route Risk Scoring Platform

**Big Data Programming Project — ST5011CEM**

> A PySpark-powered pipeline that turns raw UK bus timetable data into predicted delays, compliance classifications, and a prioritised route risk score — for a city transport authority, presented through a live interactive dashboard.

**Network:** Stagecoach Merseyside & South Lancashire (SCMY) · **Scale:** 151 real TransXChange files → 11,585 daily trips → millions of annual trip-instances

---

## ✨ Features

| | |
|---|---|
| 📥 **Real ingestion** | Custom TransXChange XML parser, zero parse errors across 151 real BODS files |
| ⚡ **True distributed processing** | PySpark partitioning, caching, broadcast joins, Spark SQL, lazy evaluation/DAG |
| 🤖 **Model comparison** | Linear Regression vs Random Forest vs Gradient-Boosted Trees, with CrossValidator tuning |
| ✅ **Compliance classifier** | Accuracy, Precision, Recall, F1, ROC-AUC + confusion matrix |
| 🎯 **Route Risk Score** | Composite metric combining predicted delay, headway irregularity & reliability |
| 🔒 **Secure storage** | SQLite, parameterised queries only — no string concatenation |
| 📊 **Live dashboard** | Streamlit + Plotly, including real-time delay prediction from the saved Spark model |

## 🛠️ Tech Stack
`PySpark` `MLlib` `SQLite` `Streamlit` `Plotly` `Pandas` `Matplotlib`

## 🚀 Quick Start

```bash
# Install dependencies (requires Java 8/11 for PySpark)
pip install -r requirements.txt

# Run the pipeline — ingests data, trains models, exports all outputs
jupyter notebook bus_delay_risk_scoring.ipynb

# Launch the dashboard
streamlit run app.py
```

## 📁 Project Structure
├── bus_delay_risk_scoring.ipynb   # Main pipeline (85 steps, 77+ figures)
├── app.py                          # Streamlit dashboard
├── requirements.txt
├── config/spark_config.py          # Spark & database configuration
├── scripts/                        # Standalone preprocessing / augmentation / ML pipeline
├── docs/                           # Architecture & database schema diagrams
├── sql/sample_queries.sql
└── data/                           # BODS timetable XML + location sample

## 📊 Data Source
[UK Bus Open Data Service](https://data.bus-data.dft.gov.uk/) — used under the Open Government Licence. Delay values are synthetically augmented (BODS retains no historical location archive) using a documented, literature-informed distribution — full justification in the accompanying report.

## ⚠️ Note on Results
Predictions demonstrate pipeline correctness and methodology rather than validated real-world accuracy, since the ground-truth delay signal is synthetic by necessity. See the report's Critical Reflection for full discussion.

## 👤 Author
ROHIT SHARMA
