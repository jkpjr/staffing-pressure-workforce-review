# Workforce Analytics Case Study
Below is the analysis of the provided context and data from People Analytics, Metrics & Workforce Insights Microsoft course capstone project via Coursera.

## 1. Workforce Question and Business Context
* **Leadership Question:** "Which region needs the most immediate HR follow-up this quarter, and what evidence-proportionate action should we recommend to the regional leader?"
* **Reporting Periods:** Q1 2026 (baseline), Q2 2026 (current).
* **Function under Focus:** Escalations Ops (Support division).
* **Business-Context Measure:** Backlog per FTE — Q2 average.

## 2. Metric-Definition Check
| Metric | Definition |
| :--- | :--- |
| **Q2 End Headcount** | Distinct EmployeeID active on 2026-06-30. |
| **Headcount Change** | Q2 End HC - Q1 End HC (Q1 End HC supplied as Begin_HC in Workforce_Movement). |
| **Screened-to-Interview Conversion (%)** | Sum interviewed ÷ sum screened, per region, Q2. Distinct from requisition fill rate. |
| **Average Time-to-Fill (days)** | Mean of (FillDate - OpenDate) for requisitions filled in Q2. |
| **Voluntary Attrition Rate (%)** | Voluntary separations Q2 ÷ beginning-of-quarter population × 100 (supplied as Begin_Population). |
| **Average Compa-Ratio** | Mean of individual compa-ratios in the scope group, reported with standard deviation. |
| **Backlog per FTE** | Business measure, Q2 average backlog volume ÷ FTE, for Escalations Ops only. |

### Organizational Roll-Up Rules
* **Q2 End Headcount:** Sum of the four regions.
* **Headcount Change:** Sum of the four regions.
* **Screened-to-Interview Conversion:** Total candidates interviewed ÷ total candidates screened across all four regions.
* **Average Time-to-Fill (days):** Weighted by Requisitions_Filled.
* **Voluntary Attrition Rate:** Total voluntary separations ÷ total Begin_Population across all four regions.
* **Average Compa-Ratio:** Weighted by N_L3_Sample.
* **Backlog per FTE:** Unweighted mean of the four regional values.

## 3. Headcount and Movement Evidence
| Region | Q1_HC | Q2_HC | HC_Change |
| :--- | :--- | :--- | :--- |
| **North** | 340 | 345 | 5 |
| **Central** | 280 | 285 | 5 |
| **South** | 210 | 205 | -5 |
| **West** | 170 | 172 | 2 |

*The South Region shows a decrease in workforce in Q2 when compared to Q1.*

## 4. Recruiting Evidence
| Region | Requisitions_Open | Screened_to_Interview_Pct | Avg_TimeToFill_Days | Requisition_Fill_Rate_Pct |
| :--- | :--- | :--- | :--- | :--- |
| **North** | 28 | 78.6 | 32 | 75.0 |
| **Central** | 24 | 75.0 | 34 | 70.8 |
| **South** | 36 | 55.6 | 45 | 50.0 |
| **West** | 16 | 75.0 | 30 | 68.8 |

*South Region has the lowest Screened-to-Interview conversion (55.6%) and Requisition Fill Rate (50%) among all regions.*

## 5. Attrition Evidence
| Region | Begin_Population | Voluntary_Sep | Voluntary_Attrition_Pct |
| :--- | :--- | :--- | :--- |
| **North** | 340 | 5 | 1.5 |
| **Central** | 280 | 4 | 1.4 |
| **South** | 210 | 15 | 7.1 |
| **West** | 170 | 3 | 1.8 |

* **Total Organization Attrition Rate:** 2.7%
* South Region makes up more than half (56%) of the voluntary leavers across all regions and has a voluntary attrition percentage nearly five times higher than its next highest peer.

## 6. Compensation Evidence
| Region | Avg_Compa_Ratio | N_L3_Sample | Compa_Ratio_StDev |
| :--- | :--- | :--- | :--- |
| **North** | 1.02 | 62 | 0.05 |
| **Central** | 0.99 | 48 | 0.06 |
| **South** | 0.98 | 40 | 0.07 |
| **West** | 1.01 | 36 | 0.06 |

*While South is lowest (0.98), it remains close to peers (0.99–1.02) and does not provide sufficient evidence to explain its high voluntary attrition rate.*

## 7. AI-Assisted Interpretation Validation
* **Supplied Interpretation:** “South is the standout region. Voluntary attrition is highest (7.1%), Screened-to-Interview conversion is lowest (55.6%), Average Time-to-Fill is longest (45 days), and Backlog per FTE is roughly double the other regions (6.8). Compensation is also the lowest — South’s Avg Compa-Ratio is 0.98, which explains why people are leaving.”
* **Decision:** **Revised** (Facts accepted, causal compensation claim rejected).
* **Evidence-Based Reason:** The descriptive metrics (7.1% attrition, 55.6% conversion, 45 days TTF, 6.8 backlog) are fully supported. However, stating the 0.98 compa-ratio *explains* why people are leaving is an unsupported causal claim. The 0.98 ratio remains close to the peer range (0.99–1.02) and lack exit-survey backing.

## 8. Integrated Workforce Finding
The data across regions and different domains suggests a strong pattern in the South Region because of its high attrition rate (7.1%), specifically in its voluntary leavers that make up more than half of the total voluntary leavers across regions. It also displays secondary operational signals such as low screened-to-interview conversion (55.6%), long average time-to-fill requisitions (45 days), a low compa-ratio context (0.98), and a backlog per FTE roughly double the average of other regions.

## 9. Follow-Up Action Comparison
* **Option A:** HR leaders in the South Region investigate the root causes of the high voluntary attrition rate.
* **Option B:** HR leaders examine the recruiting process in the South Region to identify bottlenecks causing low screened-to-interview conversion and long time-to-fill.
* *Comparison:* Option A is the strongest fit because it directly targets the primary signal (7.1% voluntary attrition), whereas Option B addresses secondary operational friction.

## 10. Recommended Action and Owner
* **Recommended Action:** Option A - Investigate the high attrition rate in the South Region.
* **Accountable Owner:** South HR Director.
* **Timing:** By Q3 of 2026.

## 11. Limitation or Next Evidence Need
The data on compensation is limited because it shows region-level aggregations, failing to provide a more granular look into the compensation distribution within each region rather than just among regions.

## 12. Copilot-Use Record
* **Prompt:** "how do I compare compa-ratios only within the controlled, matching groups when they only gave me region-level data?"
* **AI Output:** "By looking at your data source ('Compensation context by region - L3 sample'), the data is already pre-scoped to Job Level 3 (L3) and broken down by Region. So, displaying that specific table satisfies the requirement because the control (Job Level L3) is already accounted for in the dataset!"
* **Decision:** Accept
* **Evidence-Based Reason:** The provided dataset explicitly restricts the sample to Job Level 3 (L3) across regions. Therefore, displaying this table directly fulfills the requirement to present compa-ratios within controlled, matching job-level groups without needing further segment filtering.
