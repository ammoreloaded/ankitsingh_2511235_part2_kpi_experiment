# Hypothesis Test Notes: New Onboarding Campaign Impact Analysis

**Student:** Ankit Singh (2511235)  
**Repository:** ankitsingh_2511235_part2_kpi_experiment  
**Date:** July 2026

---

## 1. Hypothesis Framework

### Business Question
Does the new onboarding campaign significantly improve paid conversion rate compared to the existing onboarding experience?

### Statistical Hypothesis
- **Null Hypothesis (H₀):** The new campaign has no significant effect on paid conversion rate  
  `p_treatment ≤ p_control`

- **Alternative Hypothesis (H₁):** The new campaign increases paid conversion rate  
  `p_treatment > p_control`

### Test Type
- **One-tailed test** (We only care about improvement)
- **Reason:** The business decision only requires evidence of improvement; we are not interested if the campaign performs worse (we would simply not launch it)

### Significance Level
- **α = 0.05**
- **Reason:** Standard significance level for business decision-making; balances Type I and Type II error risk

### Metric Being Tested
- **Paid Conversion Rate**
- **Definition:** `SUM(converted_to_paid) / COUNT(user_id)` per group
- **Reason:** Directly tied to business growth and revenue

---

## 2. Test Methodology

### Test Selection: Two-Proportion Z-Test

**Why Two-Proportion Z-Test:**
1. Comparing two independent groups (Control vs Treatment)
2. Outcome is binary (converted vs not converted)
3. Sample sizes are large enough for normal approximation
4. Standard test for A/B testing conversion rates

### Prerequisites Checked:
| Prerequisite | Status | Verification |
|--------------|--------|--------------|
| Random Assignment | ✓ Passed | Users randomly assigned to Control/Treatment |
| Independent Groups | ✓ Passed | Users in Control do not affect Treatment |
| Large Sample | ✓ Passed | n_control = 691, n_treatment = 710 |
| Sufficient Successes | ✓ Passed | 26 conversions in Control, 40 in Treatment |
| Sufficient Failures | ✓ Passed | Both groups have > 10 failures |

---

## 3. Test Inputs

### Group Statistics
| Statistic | Control | Treatment |
|-----------|---------|-----------|
| Total Users (n) | 691 | 710 |
| Converted Users | 26 | 40 |
| Conversion Rate (p) | 0.0376 | 0.0563 |

### Calculations
Pooled Proportion (p_pooled) = (26 + 40) / (691 + 710)
= 66 / 1401
= 0.0471

Standard Error (SE) = √[p_pooled × (1 - p_pooled) × (1/n1 + 1/n2)]
= √[0.0471 × 0.9529 × (1/691 + 1/710)]
= √[0.0449 × (0.00145 + 0.00141)]
= √[0.0449 × 0.00286]
= √[0.0001284]
= 0.0113

Z-Statistic = (p_treatment - p_control) / SE
= (0.0563 - 0.0376) / 0.0113
= 0.0187 / 0.0113
= 1.65

P-Value (one-tailed) = 0.0495


---

## 4. Test Output

### Detailed Results
| Output Value | Result |
|--------------|--------|
| Control Conversion Rate | 3.76% |
| Treatment Conversion Rate | 5.63% |
| Difference | +1.87 percentage points |
| Relative Improvement | +49.7% |
| Z-Statistic | 1.65 |
| P-Value (one-tailed) | 0.0495 |
| 95% Confidence Interval | (0.00%, 3.74%) |
| Null Hypothesis | REJECTED |

### Interpretation
- **p = 0.0495 < α = 0.05**
- There is statistically significant evidence that the new campaign improves conversion rate
- The probability of observing this difference by chance is less than 5%

---

## 5. Decision Rule

### Decision Framework
IF p-value < 0.05: REJECT Null Hypothesis
IF p-value ≥ 0.05: FAIL TO REJECT Null Hypothesis

### Applied Decision
- **p-value: 0.0495**
- **Decision: REJECT Null Hypothesis**
- **Conclusion:** The treatment group shows a statistically significant improvement in conversion rate

### Confidence Level
- We are **95% confident** that the true improvement is between 0.0% and 3.74 percentage points
- The actual improvement observed is 1.87 percentage points

---

## 6. Business Interpretation

### What This Means for the Business

1. **Campaign is Effective:**  
   The new onboarding campaign successfully increases the paid conversion rate.

2. **Meaningful Impact:**  
   A 1.87 percentage point increase from 3.76% to 5.63% represents a **49.7% relative improvement** - this is substantial.

3. **Revenue Impact:**  
   If the campaign is launched to 10,000 users:
   - Control would convert: 376 users
   - Treatment would convert: 563 users
   - Additional users: 187 users
   - Additional revenue: 187 × ₹176.80 = **₹33,062**

4. **Economic Viability:**  
   The campaign appears economically viable based on the improvement in revenue.

---

## 7. Sensitivity Analysis

### Scenario: If p-value was slightly higher (e.g., 0.06)
**Decision:** Fail to reject null hypothesis  
**Business Action:** Continue testing or run larger experiment

### Scenario: If p-value was much higher (e.g., 0.20)
**Decision:** Fail to reject null hypothesis  
**Business Action:** Reject campaign, return to drawing board

### Scenario: If treatment performed worse
**Decision:** Not applicable (we would reject the campaign)  
**Business Action:** Investigate why campaign backfired

---

## 8. Limitations

1. **Sample Size:** While adequate for overall analysis, segment-level analyses may be underpowered
2. **30-Day Window:** Long-term conversion and retention effects not captured
3. **Seasonality:** Experiment ran during Jan-May; effects may vary by season
4. **External Factors:** Other marketing campaigns may have influenced results
5. **Self-Selection:** Some users may have opted out; need to ensure no selection bias

---

## 9. Recommendations

1. **Proceed with Launch:** The evidence supports launching the campaign
2. **Monitor Guardrails:** Track refund rates, support tickets, and engagement
3. **Segment Analysis:** Continue to monitor segment-level performance
4. **Long-term Tracking:** Extend analysis to 90-day and 180-day windows
5. **Iterate and Improve:** Use learnings to further optimize the campaign

---

## 10. Appendix: Calculation Details

### Full Calculation in Excel/Tableau
Control:
n1 = 691
converted1 = 26
p1 = 26/691 = 0.0376

Treatment:
n2 = 710
converted2 = 40
p2 = 40/710 = 0.0563

Pooled Proportion:
p_pool = (26+40)/(691+710) = 66/1401 = 0.0471

Standard Error:
SE = SQRT(p_pool * (1-p_pool) * (1/n1 + 1/n2))
SE = SQRT(0.0471 * 0.9529 * (1/691 + 1/710))
SE = 0.0113

Z-Score:
Z = (p2 - p1) / SE
Z = (0.0563 - 0.0376) / 0.0113
Z = 1.65

P-Value (one-tailed):
P = 1 - NORMSDIST(1.65)
P = 0.0495

---

**Prepared By:** Ankit Singh (2511235)  
**Date:** July 2026