# Web Analytics Mini-Project — Website Traffic, Sessions & Conversion (WIP)

**Goal:** Analyze website session data to understand how **traffic source** relates to **engagement** (session duration, time on page, page views) and **conversion behavior**, and to highlight why relying only on averages can be misleading.

**Dataset:** “Website Traffic” (Kaggle) — each row represents a **single session** (not a unique user or aggregated day).  
**Source:** [Kaggle — Website Traffic (Anthony Therrien)](https://www.kaggle.com/datasets/anthonytherrien/website-traffic)

---

## What’s inside
- **Notebook 01 — [Session Overview (EDA)](notebooks/01_Session_Overview.ipynb):** distribution checks, mean vs median, long-tail behavior, and early relationships (e.g., page views vs session duration).
- **Notebook 02 — [Cleaning & Analysis Prep](notebooks/02_Clean_and_Analysis_Prep.ipynb):** data cleaning and creation of cleaned/aggregated tables used for reporting-style insights.

---

## Key questions
1. How are **Session Duration** and **Page Views** distributed? Is there a long tail?  
2. How different are **mean vs median** values (and what does that imply)?  
3. How does **Bounce Rate** vary by **Traffic Source**?  
4. Do users with more **Previous Visits** show higher conversion behavior?  
5. What interpretation risks appear when using only averages?

---

## Variables
- **Page Views** (discrete quantitative)  
- **Session Duration** (continuous quantitative, minutes)  
- **Bounce Rate** (continuous, proportion)  
- **Traffic Source** (categorical)  
- **Time on Page** (continuous quantitative)  
- **Previous Visits** (discrete quantitative)  
- **Conversion Rate** (continuous, proportion)

---

## Cleaning notes (current)
- Removed a small number of sessions with **Page Views = 0** (n=14). Rationale: a “session” typically implies at least one page view; these rows are likely artifacts and can skew summary metrics.

---

## Findings so far (WIP)

### Session behavior
- Most sessions are **short** (under ~2 minutes), with a **long tail** of unusually long sessions.
- Page views appear more concentrated around a mid-range (roughly 4–6 pages per session).

### Relationship: Page Views vs Session Duration
- From **1 to 5 page views**, session duration tends to increase as page views increase.
- Beyond that, sample sizes drop sharply, so averages become unstable and conclusions are tentative.

### Traffic source summary (non-technical)
- **Organic** drives the **largest volume** of sessions and shows relatively strong typical engagement.
- **Social** brings lower volume but tends to show **slightly longer sessions**, with conversion rates broadly similar.
- **Referral** is lower volume and not outstanding for duration, but shows a **slight conversion advantage** (interpret cautiously due to smaller sample size).

## Impact of previous visits on user behavior

Overall, there is no drastic jump between new and returning users. New users tend to spend slightly more time on the site, possibly because they are still exploring and are less familiar with the interface. Both new and returning users typically view a similar number of pages per session. In terms of conversion, the most loyal users (4–9 previous visits) show a slightly higher likelihood of converting, although the difference compared to the rest of the users is small.

## Do longer sessions convert better?

Longer sessions do show a slightly higher average conversion rate, but the difference between duration groups is small. Based on this dataset, it would not be reasonable to rely solely on increasing session duration as the main lever for improving conversions.


---

## How to run
1. Clone the repo
2. Create an environment and install dependencies:
   - `pip install -r requirements.txt`
3. Run notebooks in order:
   - `01_session_overview_eda.ipynb`
   - `02_cleaning_and_analysis_prep.ipynb`

---

## Next steps
- Add a compact **KPI table** by Traffic Source (engagement + conversion metrics).
- Add a small set of visuals (distributions + channel comparison).
- Export final aggregated tables to `/outputs/` for a reporting-style deliverable.

---

## Notes
This project is **work in progress**. The focus is clarity, reproducibility, and communicating insights in a business-friendly way.
