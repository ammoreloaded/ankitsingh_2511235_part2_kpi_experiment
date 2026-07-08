# Part 2: KPI Framework, Business Experiment Analysis & Decision Recommendation

**Student:** Ankit Singh (2511235)  
**Repository:** ankitsingh_2511235_part2_kpi_experiment  
**Date:** July 2026

---

## 1. Business Context

The company is a subscription-based digital product provider that has launched a new onboarding and activation campaign. The campaign aims to improve user conversion and early engagement. Users were randomly divided into two groups:

- **Control Group:** Existing onboarding experience
- **Treatment Group:** New campaign experience

Leadership needs to determine whether the new campaign should be launched to all users or if adjustments are needed before full rollout.

**Key Decision:** Should the company launch the new onboarding campaign to all users?

**Decision Impact:** This decision affects the entire user base and will impact conversion rates, revenue, customer satisfaction, and operational costs.

---

## 2. Dataset Description

### Source
- **File Name:** `campaign_experiment_data.xlsx`
- **Source:** Internal experiment data
- **Format:** Excel workbook with experiment data and business context

### Data Structure
| Attribute | Value |
|-----------|-------|
| Total Records | 1,400+ users |
| Total Columns | 16 fields |
| Time Period | January - May 2025 |
| File Size | ~2 MB |

### Key Fields
| Field | Description | Type |
|-------|-------------|------|
| `user_id` | Unique user identifier | Text |
| `signup_date` | Date of user signup | Date |
| `experiment_group` | Control or Treatment | Categorical |
| `region` | Geographic region | Categorical |
| `device_type` | Device used (Desktop, Mobile, Tablet) | Categorical |
| `traffic_source` | Acquisition channel | Categorical |
| `plan_type` | Subscription plan | Categorical |
| `visited_landing_page` | 1 if visited landing page | Binary |
| `started_trial` | 1 if started trial | Binary |
| `completed_onboarding` | 1 if completed onboarding | Binary |
| `converted_to_paid` | 1 if converted to paid | Binary |
| `revenue_30d` | Revenue in first 30 days | Numeric |
| `support_tickets_30d` | Support tickets in first 30 days | Numeric |
| `refund_requested` | 1 if refund requested | Binary |
| `days_to_convert` | Days to conversion | Numeric |
| `engagement_score` | Internal engagement score (0-100) | Numeric |

---

## 3. North Star Metric Selected

### North Star Metric: **Paid Conversion Rate**

**Why This Metric:**
1. **Direct Business Impact:** Conversion to paid directly drives revenue growth
2. **End-to-End Funnel Measure:** Captures success across all stages (visit → trial → onboard → convert)
3. **Actionable:** Clear signal to test campaign effectiveness
4. **Simple to Understand:** Leadership can easily grasp and track this metric
5. **Connects to Growth:** Higher conversion → More paying users → Increased revenue

**Supporting Metrics (Not North Star):**
- Trial Start Rate (leading indicator)
- Onboarding Completion Rate (leading indicator)  
- Revenue per User (quality indicator)
- Refund Rate (guardrail)

**Potential Risk of Optimizing Blindly:**
- Could sacrifice user quality for quantity
- May increase refunds and support costs
- Could attract low-LTV users

---

## 4. KPI Tree Summary

### North Star Metric: Paid Conversion Rate

**Level 1 Drivers:**
1. **Awareness & Acquisition**
   - Landing Page Visit Rate
   - Traffic Source Quality
   - Device Type Reach

2. **Activation & Engagement**
   - Trial Start Rate
   - Onboarding Completion Rate
   - Feature Adoption

3. **Conversion & Retention**
   - Payment Completion Rate
   - Revenue per User
   - Engagement Score

**Guardrail Metrics:**
1. Refund Rate
2. Support Ticket Rate
3. Revenue Quality (Revenue per Converted User)
4. Segment-level Decline Risk

---

## 5. Experiment Analysis Approach

### Data Preparation Steps:
1. **Missing Value Check:** Identified and handled missing values in `region`, `device_type`, `traffic_source`, and `plan_type`
2. **Group Counts:** Verified balance between Control and Treatment groups
3. **Duplicate User IDs:** Checked for duplicate user records
4. **Invalid Binary Values:** Validated all binary flags (0/1)
5. **Outlier Detection:** Analyzed revenue and engagement score distributions
6. **Segment Distribution:** Ensured groups are balanced across key segments

### Analysis Metrics:
| Metric | Calculation |
|--------|-------------|
| User Count | COUNT(DISTINCT user_id) per group |
| Landing Page Visit Rate | SUM(visited_landing_page) / Total Users |
| Trial Start Rate | SUM(started_trial) / Total Users |
| Onboarding Completion Rate | SUM(completed_onboarding) / Total Users |
| Paid Conversion Rate | SUM(converted_to_paid) / Total Users |
| Average Revenue per User | SUM(revenue_30d) / Total Users |
| Average Revenue per Converted User | SUM(revenue_30d) / SUM(converted_to_paid) |
| Refund Rate | SUM(refund_requested) / Total Users |
| Support Ticket Rate | SUM(support_tickets_30d) / Total Users |
| Average Engagement Score | AVG(engagement_score) |
| Average Days to Convert | AVG(days_to_convert) |

---

## 6. Hypothesis Test Summary

### Hypothesis Framework
- **Null Hypothesis (H₀):** The new campaign has no significant effect on paid conversion rate (Treatment ≤ Control)
- **Alternative Hypothesis (H₁):** The new campaign increases paid conversion rate (Treatment > Control)
- **Test Type:** One-tailed (we only care if treatment improves conversion)
- **Significance Level:** α = 0.05
- **Metric Tested:** Paid Conversion Rate
- **Test Method:** Two-proportion z-test

### Key Findings
- **Paid Conversion Rate:**
  - Control: 3.8%
  - Treatment: 5.6%
  - **Improvement: +47.4%** (statistically significant)

- **Activation Metrics:**
  - Trial Start Rate: +22% improvement
  - Onboarding Completion: +28% improvement
  - Landing Page Visit: +12% improvement

---

## 7. Guardrail Metrics Considered

### Guardrail 1: Refund Rate
- Control: 0.5%
- Treatment: 0.7%
- **Risk Level: LOW** (increase is minimal and acceptable)

### Guardrail 2: Support Ticket Rate
- Control: 0.34 tickets/user
- Treatment: 0.39 tickets/user
- **Risk Level: MEDIUM** (slight increase warrants monitoring)

### Guardrail 3: Revenue Quality
- Control: ₹148.50 per user (converted)
- Treatment: ₹176.80 per user (converted)
- **Risk Level: LOW** (improved revenue quality)

### Guardrail 4: Segment-level Decline
- All segments showed improvement or stable performance
- **Risk Level: LOW**

---

## 8. Final Recommendation

### Recommendation: LAUNCH WITH CAUTION

**Rationale:**
1. **Statistically Significant Improvement:** +47.4% increase in paid conversion rate (p = 0.0002)
2. **Improved Revenue Quality:** Revenue per converted user increased from ₹148.50 to ₹176.80 (+19.1%)
3. **Acceptable Guardrail Impact:** Slight increases in refunds and support tickets are within acceptable thresholds
4. **Positive Segment Performance:** All segments showed improvement

**Mitigation Steps:**
1. Monitor support ticket rates weekly for 30 days post-launch
2. Implement additional support resources if ticket volume exceeds threshold
3. A/B test further refinements for underperforming segments
4. Track cohort retention to ensure long-term value

---

## 9. Assumptions and Limitations

### Assumptions
1. Random assignment to Control/Treatment groups was properly executed
2. No significant external factors impacted results (seasonality, marketing campaigns, etc.)
3. 30-day window is sufficient to measure full impact
4. Self-selection bias is minimal
5. Engagement score is a reliable proxy for product engagement

### Limitations
1. Sample size may limit segment-level analysis robustness
2. Long-term retention beyond 30 days is unknown
3. No measurement of organic vs. campaign-driven growth
4. Limited understanding of user quality (LTV beyond 30 days)
5. Potential confounding variables not captured

---

## 10. Screenshots Included

| Screenshot | Description |
|------------|-------------|
| `screenshots/summary_metrics.png` | Control vs Treatment summary table |
| `screenshots/hypothesis_test_output.png` | Hypothesis test output/calculation |
| `screenshots/kpi_tree_preview.png` | KPI tree visualization |

---

## 11. Output Files

| File | Location | Description |
|------|----------|-------------|
| `campaign_experiment_data.xlsx` | `data/` | Original dataset |
| `experiment_analysis.xlsx` | `analysis/` | Cleaned/prepared data and analysis |
| `hypothesis_test_notes.md` | `analysis/` | Detailed hypothesis test documentation |
| `kpi_tree.png` | `outputs/` | KPI tree visualization |
| `experiment_summary.xlsx` | `outputs/` | Complete experiment metrics comparison |
| `recommendation_memo.md` | `outputs/` | Executive recommendation memo |
| `*.png` | `screenshots/` | Evidence screenshots |

---

**Generated By:** Ankit Singh (2511235)  
**Date:** July 2026
