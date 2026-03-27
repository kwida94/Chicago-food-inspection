# Restaurant Health Inspection Analysis (2024–2026)

## Overview

For this project, I analyzed restaurant health inspection data from Chicago's public open data portal to understand compliance trends and risk patterns. The dataset covers inspections from January 2024 through February 2026.

My main goal was to take a large, messy dataset and turn it into something I could actually learn from — cleaning it up, organizing it, and then using Excel and Power Query to find patterns in the results.

**Dataset summary:**
- Total inspections analyzed: 39,365
- Duplicate inspections found: 0
- Time period: January 2024 – February 2026

---

## Questions I Wanted to Answer

- How often do inspections pass, fail, or pass with conditions?
- Do higher-risk facilities fail more often than lower-risk ones?
- Does the number of violations affect whether a facility passes or fails?
- Which violations come up most frequently?
- Have compliance rates changed over time?

---

## Tools Used

- **Excel** – data exploration and visualization
- **Power Query** – data cleaning and transformation
- **Pivot Tables** – summarizing results by category

---

## Data Cleaning

Before doing any analysis, I used Power Query to clean and standardize the raw data. This included removing irrelevant columns, filtering to the right date range, standardizing the risk and result categories, and extracting violation counts from the violation text field.

![Power Query transformation steps](02_outputs/power-query.png)

---

## Key Findings

### 1. Overall Inspection Results

Across all 39,365 inspections, results were fairly evenly split between pass and fail — but nearly 60% of inspections either failed outright or required corrective action before passing.

- **Pass:** 40.11%
- **Fail:** 38.88%
- **Pass w/ Conditions:** 21.01%

![Inspection Results Distribution](02_outputs/inspection-results-distribution.png)

---

### 2. Violation Count Is a Strong Predictor of Failure

One of the clearest patterns I found was the relationship between the number of violations cited and whether a facility passed or failed. Facilities with just 1–2 violations passed about 77% of the time. That number dropped sharply as violations increased — facilities with 6 or more violations failed about 50% of the time.

![How Inspection Results Change as Violations Increase](02_outputs/outcomes-by-violation-count.png)

---

### 3. Lower-Risk Facilities Actually Fail More Often

This was probably the most surprising finding. I expected high-risk facilities (Risk 1) to have the highest failure rates, but the data showed the opposite pattern:

| Risk Level | Failure Rate |
|---|---|
| Risk 3 (Low) | 51.66% |
| Risk 2 (Medium) | 41.03% |
| Risk 1 (High) | 38.14% |

Risk 1 (High) facilities — places that handle raw meat, cooking, and complex food prep — actually had the lowest failure rate. Risk 3 (Low) facilities, which typically have simpler operations, failed more than half the time. This suggests that risk classification alone is not a reliable predictor of compliance, and that lower-risk facilities may not be receiving the same level of training or oversight.

![Failure Rate by Risk Level](02_outputs/failure-rate-by-risk-level.png)

---

### 4. Compliance Rates Are Stable Over Time

Looking at inspection outcomes month by month, the overall distribution stayed fairly consistent from January 2024 through February 2026. There were some months with slightly higher failure rates, but nothing that pointed to a major system-wide shift.

![Inspection Rate Over Time (2024–2026)](02_outputs/inspection-rate-over-time.png)

---

### 5. Top 10 Most Frequent Violations

The most commonly cited violations were violation codes 55, 47, and 49. These correspond to issues around food source documentation, pest prevention, and physical facility conditions. The chart below shows the 10 violation codes that appeared most often across all inspections.

![Top 10 Health Inspection Violations](02_outputs/top-10-violations.png)

---

## Full Dashboard

Here is the complete dashboard I built in Excel, combining all of the charts above into a single view.

![Restaurant Inspection Compliance & Risk Analysis Dashboard](02_outputs/Health%20Inspection%20Dashboard.png)

---

## What the Data Suggests

- **Violation count is a reliable warning sign.** Facilities with 6 or more violations are much more likely to fail. Tracking this threshold could help city inspectors or restaurant operators identify who is at risk before the next inspection.
- **Risk classification does not predict compliance.** The fact that low-risk facilities have the highest failure rates is worth investigating further. It may point to a gap in how those facilities are monitored or trained.
- **Core operational issues drive most violations.** The most frequent violations consistently relate to food source documentation, pest prevention, and facility upkeep — not complex cooking or handling issues.
- **Compliance has been stable, but failure rates remain high.** Over 38% of inspections resulting in failure is significant, and it suggests there is room for systemic improvement.

---

## Recommendations

Based on this analysis, here are a few things that might help reduce failure rates:

1. **Focus training on the most common violations.** Since violation codes 55, 47, and 49 appear far more than others, targeted training on those specific areas could have a big impact.
2. **Use violation count as an early warning metric.** Facilities approaching 5–6 violations in a single inspection could be flagged for follow-up before their next scheduled visit.
3. **Investigate why low-risk facilities fail at higher rates.** This is counterintuitive enough that it deserves a closer look — it may reveal gaps in oversight or training for certain facility types.
4. **Track repeat offenders.** The current analysis looks at each inspection in isolation. A follow-up analysis of facilities with repeated failures would help identify where intervention is most needed.

---

## Next Steps

- Build an interactive dashboard in Tableau to make the results easier to explore
- Use SQL to analyze re-inspection patterns and repeat offenders
- Look into geographic trends — are certain neighborhoods or zip codes seeing higher failure rates?
- Investigate the risk level finding in more detail, possibly by breaking it down by facility type
