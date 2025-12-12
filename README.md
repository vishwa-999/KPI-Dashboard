# 💰 Dynamic 13-Week Cash Flow Forecast (Growth Curve Model)

This Google Colab notebook provides a dynamic, predictive 13-week cash flow model specifically designed for **Growth Curve** companies experiencing high revenue volatility and "lumpy" expense cycles.

The model is built entirely in Python using **Pandas** for data manipulation and **Plotly** for interactive visualization. It moves beyond simple averaging to highlight critical short-term liquidity risks.

---

## 🌟 Key Features & Dashboard Overview

The dashboard is structured to give immediate visibility into the company's short-term financial health, flagging the exact week cash reserves will be lowest.

### Financial Health Tickers

| KPI | Calculation Logic | Growth Curve Relevance |
| :--- | :--- | :--- |
| **Minimum Cash Balance** | `MIN(Closing Cash Balance for Weeks 1-13)` | **CRITICAL RISK ALERT.** The lowest cash point in the next quarter, determining if proactive action (delaying AP, seeking credit) is needed. |
| **Cash Runway (Weeks)** | `Current Cash / Avg. Weekly Net Burn` | **Survival Metric.** How long the company can survive without new financing or a change in burn rate. |
| **Cash Conversion Ratio** | `Total Inflows / Total Outflows` | **Efficiency Metric.** Measures if the company's growth is cash-efficient (ratio $> 1.0$ is ideal). |

---

## 📈 Visual Forecast Summary

### 1. 13-Week Closing Cash Balance (Risk Monitor)

This line chart shows the rolling cash balance, visually identifying when and where the company will face its tightest liquidity constraint (the Minimum Cash Balance).

![Closing Cash Balance Forecast](images/cash_balance_forecast.png)

### 2. Weekly Net Flow Breakdown

This chart shows the week-over-week net change in cash. Negative bars (red) indicate a week where scheduled outflows (like Payroll or Ad Spend) exceed inflows.

![Net Cash Flow Breakdown](images/net_flow_waterfall.png)

---

## 🛠️ Setup and Usage (In Google Colab)

To run this dynamic forecast, open the notebook in Google Colab and execute the cells sequentially.

### Prerequisites

* A Google Account (to run Colab).
* **Libraries:** `Pandas`, `NumPy`, `Plotly`, and `Kaleido` (for static image export) are used.

### Step-by-Step Guide

The notebook is divided into three functional parts:

#### 1. Data Initialization (The Lumpy Logic)
* **Action:** **MANUAL INPUT REQUIRED.** Locate the `flow_data` dictionary and `STARTING_CASH` variable.
* **Goal:** Replace the dummy values with your company's specific, *scheduled* payments. For example, enter the full amount of payroll only on its specific payday week (e.g., Week 4, Week 8, etc.) and $\$0$ on all other weeks. This is the heart of the risk model.

#### 2. Core Model Calculation
* **Action:** Run the cell containing the `create_cashflow_df()` function.
* **Goal:** This function applies the rolling balance formulas to generate the complete 13-week forecast table, calculating the Net Cash Flow and Closing Cash Balance for every week.

#### 3. Dashboard Generation & Export
* **Action:** Run the final cells.
* **Goal:** This step automatically calculates the **KPIs**, generates the interactive **Plotly charts**, and saves the charts as `.png` files to the local `images/` directory for use in this `README.md`.

---
