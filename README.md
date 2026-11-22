# Workforce Analytics Case Study
Below is the analysis of the provided context and data from People Analytics, Metrics & Workforce Insights Microsoft course capstone project via Coursera.

## 1. Workforce Question and Business Context

The leaders ask "Which region needs the most immediate HR follow-up this quarter, and what evidence-proportionate action should we recommend to the regional leader?"

The Business Context includes:

- Reporting periods: Q1 2026 (baseline), Q2 2026 (current).

- Function under focus: Escalations Ops (Support division).

- Business-context measure: Backlog per FTE — Q2 average.

## 2. Metric-Definition Check

| Metric | Definition |
| :--- | :--- |
| Q2 End Headcount | Distinct EmployeeID active on 2026-06-30. |
| Headcount Change | Q2 End HC - Q1 End HC. Q1 End HC is supplied as Begin_HC in the Workforce_Movement sheet. |
| Screened-to-Interview Conversion (%) | Sum interviewed ÷ sum screened, per region, Q2. Distinct from requisition fill rate (Requisitions_Filled ÷ Requisitions_Open). |
| Average Time-to-Fill (days) | Mean of (FillDate - OpenDate) for requisitions filled in Q2. |
| Voluntary Attrition Rate (%) | Voluntary separations Q2 ÷ beginning-of-quarter population × 100. The denominator is the beginning-of-quarter population supplied as Begin_Population in the Attrition_Summary sheet, not an average of monthly snapshots. |
| Average Compa-Ratio | Mean of individual ompa-ratios in the scope group, reported with its standard deviation. |
| Backlog per FTE | Business measure, Q2 average backlog volume ÷ FTE, for the Escalations Ops function only. |

### Organizational roll-up rule

| Measure | How to calculate the Organization value |
| :--- | :--- |
| Q2 End Headcount | Sum of the four regions. |
| Headcount Change | Sum of the four regions. |
| Screened-to-Interview Conversion | Total candidates interviewed ÷ total candidates screened, across all four regions. Not the mean of the four regional rates. |
| Average Time-to-Fill (days) | Weighted by Requisitions_Filled, each region's time-to-fill counts in proportion to the requisitions it filled. |
| Voluntary Attrition Rate | Total voluntary separations ÷ total Begin_Population, across all four regions. Not the mean of the four regional rates. |
| Average Compa-Ratio | Weighted by N_L3_Sample. |
| Backlog per FTE | Unweighted mean of the four regional values. The Escalations Ops FTE counts needed to weight it are not supplied, so label it as an unweighted mean and do not present it as a true organization rate. |

## 3. Headcount and Movement Evidence

HC = Headcount

| Region | Q1_HC | Q2_HC | HC_Change |
| :--- | :--- | :--- | :--- |
| North | 340 | 345 | 5 |
| Central | 280 | 285 | 5 |
| South | 210 | 205 | -5 |
| West | 170 | 172 | 2 |

The South Region shows a decrease in workforce in Q2 when compared to Q1.

## 4. Recruiting Evidence

| Region | Requisitions_Open | Screened_to_Interview_Pct | Avg_TimeToFill_Days | Requisition_Fill_Rate_Pct |
| :--- | :--- | :--- | :--- | :--- |
| North | 28 | 78.6 | 32 | 75.0 |
| Central | 24 | 75 | 34 | 70.8 |
| South | 36 | 55.6 | 45 | 50.0 |
| West | 16 | 75 | 30 | 68.8 |

Screened-to-Interview Conversion (%) is the Sum interviewed ÷ sum screened, per region, Q2. This is distinct from requisition fill rate where Requisitions_Filled ÷ Requisitions_Open.

Average Time-to-Fill (days) is the Mean of (FillDate - OpenDate) for requisitions filled in Q2.

From the data, South Region has the lowest Screened to Interview conversion (55.6%) and Requisition Fill Rate (50%) among the regions.

## 5. Attrition Evidence

Attrition recorded between the end of Q1 and Q2.

| Region | Begin_Population | Voluntary_Sep | Voluntary_Attrition_Pct |
| :--- | :--- | :--- | :--- |
| North | 340 | 5 | 1.5 |
| Central | 280 | 4 | 1.4 |
| South | 210 | 15 | 7.1 |
| West | 170 | 3 | 1.8 |

Total Attrition Rate (%) 2.7

South Region makes up more than half (56%) of the voluntary leavers across all regions and has almost five times than its next highest voluntary attrition percentage.

Voluntary attrition percentage uses the formula: Voluntary separations Q2 ÷ beginning-of-quarter population × 100.

The data suggests that there’s an elevated patter of voluntary attrition in the South Region.

## 6. Compensation Evidence

| Region | Avg_Compa_Ratio | N_L3_Sample | Compa_Ratio_StDev |
| :--- | :--- | :--- | :--- |
| North | 1.02 | 62 | 0.05 |
| Central | 0.99 | 48 | 0.06 |
| South | 0.98 | 40 | 0.07 |
| West | 1.01 | 36 | 0.06 |

The displayed data shows region-level Compa-ratios of salaries among the same job level of 3 and group. Because this is a region-level aggregation, there is a need to investigate a more granular sets of data in each region, especially in the South Region that shows a 0.98 average Compa-ratio of compensation.

It is important to note that while South is lowest (0.98), it remains close to peers (0.99-1.02) and is not enough to explain its high voluntary attrition rate.

## 7. AI-Assisted Interpretation Validation

Copilot’s interpretation in answering the leadership question, verbatim: “South is the standout region. Voluntary attrition is highest (7.1%), Screened-to-Interview conversion is lowest (55.6%), Average Time-to-Fill is longest (45 days), and Backlog per FTE is roughly double the other regions (6.8). Compensation is also the lowest — South’s Avg Compa-Ratio is 0.98, which explains why people are leaving.”

This interpretation needs to be revised. The facts are correct. South is indeed the standout region with the voluntary attrition (7.1%), the lowest screened-to-Interview conversion (55.6%), the longest Average Time-to-Fill (45 days), the biggest Backlog per FTE (6.8), and the lowest Compa-ratio (0.98). However, it states that the low Compa-ratio of 0.98 is the cause of high attrition, which is an unsupported causal statement. A 0.98 Compa-ratio is still near peer range of 0.99-1.02 and the data does not have additional evidence to conclude that it’s the cause of high attrition rate in the region.

## 8. Integrated Workforce Finding

The data across regions and different domains suggests a strong pattern in the South Region because of its high attrition rate (7.1%), specifically in its voluntary leavers that makes up more than half of the total voluntary leavers across regions. It also has secondary signals such as low screened-to-interview conversion (55.6%), long average time-to-fill requisitions (45 days), low Compa-ratio in compensation (0.98), and a backlog per FTE that is roughly double the average of other regions.

## 9. Follow-Up Action Comparison

Two needed actions can be derived from what the data shows. Option A is that HR leaders in the South Region investigate the cause of high attrition rate. Option B is for HR leaders to look into the process of recruitment in the South Region to find the cause of a low screened-to-interview conversion and long average time-to-fill requisitions.

## 10. Recommended Action and Owner

The most recommended from the two derived required actions is Option A because it shows a more concerning pattern of 7.1% attrition compared to its peer range of 1.4-1.8%. It is most recommended that South HR director investigates the high attrition rate in the South Region by Q3 of 2026.

## 11. Limitation or Next Evidence Need

The data on compensation is limited because it shows the region-level, failing to provide a more granular look into the compensation distribution within each region and not just among the regions.

## 12. Copilot-Use Record

**Prompt:** "how do I compare Compa-ratios only within the controlled, matching groups when they only gave me region-level data?"

**AI Output:** “By looking at your data source ("Compensation context by region — L3 sample"), the data is already pre-scoped to Job Level 3 (L3) and broken down by Region.

So, displaying that specific table satisfies the requirement because the control (Job Level L3) is already accounted for in the dataset!”

**Decision:** Accept

**Evidence-Based Reason:**

The provided dataset explicitly restricts the sample to Job Level 3 (L3) across regions. Therefore, displaying this table directly fulfills the requirement to present compa-ratios within controlled, matching job-level groups without needing further segment filtering.
