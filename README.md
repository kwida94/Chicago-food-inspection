# Restaurant Health Inspection Analysis (2024–2026)

## Overview

I pulled restaurant health inspection data from Chicago's open data portal and used it as a practice project to get more comfortable with Excel and Power Query. The data covers inspections from January 2024 through February 2026.

I wanted to see if I could find any patterns in who passes, who fails, and why.

- Total inspections: 39,365
- Duplicates: 0
- Time period: January 2024 – February 2026

---

## Questions I Tried to Answer

- How are inspections split between pass, fail, and pass with conditions?
- Do higher-risk facilities fail more often?
- Does having more violations make you more likely to fail?
- Which violations show up the most?
- Has anything changed over time?

---

## Tools

- Excel
- Power Query
- Pivot Tables

---

## Data Cleaning

Before I could do any analysis I had to clean up the raw data pretty heavily. I used Power Query to remove columns I didn't need, filter to the right date range, and pull out violation counts from the violation description text.

![Power Query transformation steps](02_outputs/power-query.png)

---

## What I Found

### Overall Results

About 40% of inspections passed, 39% failed, and 21% passed with conditions. I thought pass rates would be higher than that — almost 60% of inspections ended in either a fail or some kind of required fix.

- Pass: 40.11%
- Fail: 38.88%
- Pass w/ Conditions: 21.01%

![Inspection Results Distribution](02_outputs/inspection-results-distribution.png)

---

### More Violations = More Likely to Fail

This one made a lot of sense once I saw it. Facilities with only 1–2 violations passed around 77% of the time. Once you hit 6 or more violations, the failure rate jumped to about 50%. The more things wrong, the worse the outcome.

![How Inspection Results Change as Violations Increase](02_outputs/outcomes-by-violation-count.png)

---

### Low-Risk Facilities Actually Failed More

This surprised me. I assumed high-risk facilities (the ones handling raw meat, full cooking, etc.) would fail the most. But it was the opposite:

| Risk Level | Failure Rate |
|---|---|
| Risk 3 (Low) | 51.66% |
| Risk 2 (Medium) | 41.03% |
| Risk 1 (High) | 38.14% |

Low-risk facilities failed more than half the time. I'm not totally sure why — maybe they get less training, or they're not as focused on food safety since they're doing simpler things. Either way it's not what I expected.

![Failure Rate by Risk Level](02_outputs/failure-rate-by-risk-level.png)

---

### Results Have Been Pretty Consistent Over Time

Looking month by month from 2024 through early 2026, the pass/fail split didn't change much. There were a few spikes here and there but nothing that looked like a big trend.

![Inspection Rate Over Time (2024–2026)](02_outputs/inspection-rate-over-time.png)

---

### Most Common Violations

The top violation codes were 55, 47, and 49 — by a lot. Code 55 showed up roughly twice as often as anything else. These codes deal with things like food source documentation, pest prevention, and facility conditions.

![Top 10 Health Inspection Violations](02_outputs/top-10-violations.png)

---

## Full Dashboard

Here's the full Excel dashboard I put together with all the charts.

![Restaurant Inspection Compliance & Risk Analysis Dashboard](02_outputs/Health%20Inspection%20Dashboard.png)

---

## Takeaways

The violation count finding was probably the most useful — it's a pretty clear signal. If a facility racks up 6+ violations in one inspection, there's a 50% chance it fails. That seems like something worth paying attention to.

The risk level finding was more confusing. I went in thinking Risk 1 (High) facilities would have the worst numbers, but they actually did the best. I'd want to dig into that more before drawing any big conclusions.

The most common violations being in pest prevention and food sourcing also stood out. Those aren't complicated things — they're more about consistency and habits than skill.

---

## What I'd Do Next

- Learn Tableau and rebuild this as an interactive dashboard
- Use SQL to look at repeat offenders — facilities that keep failing inspections
- Map the results by neighborhood to see if location matters
- Break down the risk level finding by facility type to understand it better
