#  B2B Sales Pipeline & CRM Analytics Case Study

##  Executive Summary
This project analyzes B2B CRM sales performance data to identify key drivers of deal closure, evaluate sector-level variations, and assess sales cycle dynamics. Using non-parametric statistical testing and correlation analysis, the project delivers actionable business recommendations for sales pipeline optimization.

---

## Key Findings & Business Insights

1. **Sector Independence (Chi-Square Test):**
   * **Result:** Win rates across all 10 industry sectors remain virtually identical (~61% to 64.8%).
   * **Statistical Validation:** $\chi^2 = 2.8313$, $p\text{-value} = 0.9706$ ($p > 0.05$).
   * **Takeaway:** Client industry sector has **no statistically significant impact** on deal outcome. The sales team should not heavily segment marketing or sales strategy strictly by sector.

2. **Sales Cycle vs. Deal Value (Spearman Rank Correlation):**
   * **Result:** No significant linear or monotonic relationship between `sales_cycle_days` and `close_value` among won deals ($r \approx 0$).
   * **Takeaway:** Deal size does not dictate deal length. Small $500 deals and large $25,000+ Enterprise deals close across similar time horizons (2 to 120+ days).

3. **Data Architecture & CRM Limitations:**
   * **Insight:** Lost deals (`is_won == 0`) contain structural zeros (`close_value == $0`).
   * **Impact:** Identified and accounted for data structure limitations to prevent data leakage in predictive evaluation.

---

##  Data & Methodology

* **Language & Libraries:** Python 3.x | `pandas`, `numpy`, `scipy.stats`, `seaborn`, `matplotlib`
* **Statistical Methods Used:**
  * **Win Rate Aggregation:** Percentage breakdown across sectors.
  * **Chi-Square Test of Independence:** Testing relation between categorical features (`sector` vs `is_won`).
  * **Spearman Rank Correlation:** Assessing monotonic relationships on skewed numerical distributions (`sales_cycle_days` vs `close_value`).

---

##  Visualizations

### Sales Cycle Days vs. Close Value (Won Deals)
![Scatter Plot](sales_cycle_vs_value.png)

---

## 💡 Recommendations for Business

1. **Standardize Sales SLAs:** Since enterprise and small-tier deals take similar amounts of time to close, introduce tiered SLA guidelines so high-value deals receive priority resources.
2. **Focus Beyond Sector Segmentation:** Reallocate sales training from sector-specific pitches to deal velocity management and pipeline tracking.

