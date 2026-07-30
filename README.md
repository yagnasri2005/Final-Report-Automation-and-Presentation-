# Final Report, Automation & Presentation

## Objective

Create a final executive report, automate the data pipeline, and submit a clean, complete set of deliverables for the Data Analytics Internship.

---

## Contents

| File | Description |
|---|---|
| `Executive_Summary_Report.pdf` | **2-page executive report** — key findings, dashboard visual, top 5 insights, 3 business recommendations |
| `automation_pipeline.py` | **Automation script** — loads raw data, cleans it, saves processed output, calculates KPIs, exports to Excel |
| `cleaned_superstore.csv` | Source ("raw") dataset used by the pipeline |
| `processed_data.csv` | Output of the pipeline's cleaning step |
| `sales_kpi_report.xlsx` | Output Excel workbook — KPI summary, category/region breakdowns, monthly trend |
| `pipeline.log` | Log output from the most recent pipeline run |
| `.github/workflows/pipeline.yml` | GitHub Actions workflow — runs the pipeline automatically every day and on demand |
| `requirements.txt` | Python dependencies for this project |

---

## Running the Pipeline

```bash
pip install -r requirements.txt
python automation_pipeline.py
```

This will:
1. Load `cleaned_superstore.csv`
2. Clean it (remove duplicates, drop invalid rows, clip discount values)
3. Save the cleaned result to `processed_data.csv`
4. Calculate key KPIs (total sales, profit, orders, customers, AOV, margin, top category/region)
5. Export everything to `sales_kpi_report.xlsx` with formatted headers

---

## Automated Scheduling

### Option A — GitHub Actions (already set up in this repo)
The workflow in `.github/workflows/pipeline.yml` runs automatically **every day at 06:00 UTC**, and can also be triggered manually:
1. Go to the **Actions** tab of this repository
2. Select **Daily Sales KPI Pipeline**
3. Click **Run workflow**

No local setup required — GitHub runs it for you and commits the updated outputs back to the repo.

### Option B — Windows Task Scheduler (if running locally instead)
1. Open **Task Scheduler** → **Create Basic Task**
2. Name it "Sales KPI Pipeline", set your preferred trigger (e.g. Daily)
3. Action: **Start a program**
   - Program/script: `python`
   - Add arguments: `automation_pipeline.py`
   - Start in: the folder where this repo is cloned
4. Finish — the task will now run automatically on your schedule

---

## Project Summary

This repository is the final deliverable for a 4-task Data Analytics Internship at ApexPlanet Software Pvt. Ltd., covering:
- **Task 1–2:** Exploratory Data Analysis & SQL-based data extraction
- **Task 3:** Data visualization & interactive dashboarding (Python + BI tooling)
- **Task 4:** Statistical analysis, time series forecasting, customer segmentation, and predictive modeling
- **Task 5 (this repo):** Final executive report, pipeline automation, and clean submission

Full project code for each task is available in the linked repositories below.

---

## Related Repositories

- Task 1–2 (Foundational & SQL): `github.com/yagnasri2005/SQL-Python-Integration-`
- Task 3 (Visualization & Dashboarding): `github.com/yagnasri2005/Data-Visualization-and-Dashboarding-`
- Task 4 (Advanced Analytics): `github.com/yagnasri2005/Statistical-Analysis-and-basic-predictive-modeling-`

---

## Tech Stack

Python · pandas · scikit-learn · Matplotlib/Seaborn · openpyxl · ReportLab · GitHub Actions

---

*Version: v1.0.0 — Final Submission*
