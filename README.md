# 13-Week Dynamic Cash Flow Forecast (Growth Curve Model)

This Google Colab notebook provides a dynamic, forward-looking 13-week cash flow forecast model. Unlike standard monthly forecasts that rely on simple averages, this model uses **scheduled, "lumpy" logic** to identify periods of cash strain (negative net flow) common in high-growth companies.

The model is built entirely in Python using **Pandas** for data manipulation and **Plotly** for interactive visualization.

---

## 🌟 Key Features

* **Risk-Focused Forecasting:** Payments (Payroll, Ad Spend, etc.) are scheduled to hit on specific weeks, revealing realistic cash shortfalls.
* **Automated Rolling Balance:** Calculates the continuous flow of cash across the 13 weeks.
* **Critical KPIs:** Automatically computes the **Minimum Cash Balance**, **Cash Runway**, and **Cash Conversion Ratio**.
* **Interactive Charts:** Provides a line chart of the closing balance and a bar chart of the weekly net flow, built with Plotly.

---

## 🛠️ Setup and Usage (In Google Colab)

To use this forecast, simply open the `.ipynb` file in Google Colab and run the cells sequentially.

### Prerequisites

* A Google account (to run Colab).
* No external libraries need installation; **Pandas** and **Plotly** are standard in the Colab environment.

### Step-by-Step Guide

The notebook is structured in four main sections:

#### 1. Data Initialization
* **Goal:** Define the starting cash and the 13-week forecast data.
* **Action:** **MANUAL INPUT REQUIRED.** The `flow_data` dictionary contains the weekly forecast assumptions (e.g., Payroll only hits on Weeks 4, 8, and 12).
    * **To Customize:** Edit the values in the `flow_data` dictionary to reflect your company's specific growth projections and payment schedules.

#### 2. Core Model Calculation
* **Goal:** Apply the rolling balance logic to the data.
* **Action:** Run the cell containing the `create_cashflow_df()` function. This function automatically calculates:
    * `Total Cash In`
    * `Total Cash Out`
    * `Net Cash Flow`
    * `Opening Cash Balance` (Rolling)
    * `Closing Cash Balance` (Rolling)

#### 3. Dashboard KPIs and Tickers
* **Goal:** Calculate and display top-line financial health metrics.
* **Action:** Run this cell to generate the HTML dashboard displaying:
    * **Cash Runway:** How many weeks of operation are remaining.
    * **Minimum Cash:** The lowest projected bank balance and the week it occurs (critical risk alert).
    * **Cash Conversion Ratio:** Inflows / Outflows (ideally > 1.0).

#### 4. Visualization and Detail
* **Goal:** Plot the key financial trends and show the full data breakdown.
* **Action:** Run the final cells to generate the following:
    * **Closing Cash Balance Chart (Line Chart):** Clearly identifies the minimum cash point.
    * **Net Cash Flow Chart (Bar Chart):** Shows which weeks are cash-positive vs. cash-negative.
    * **Detailed Forecast Table:** The complete 13-week table showing all line-item figures.

---

### 📚 Why This Model is Better for Growth Companies

This model avoids the smoothing effect of traditional financial statements. By accurately scheduling large, periodic payments, it forces the user to confront the short-term liquidity risk, answering the question: **"Can we cover next week's payroll/ad bill?"**

---
