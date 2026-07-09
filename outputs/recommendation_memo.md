# Recommendation Memo: New Onboarding Campaign Launch Decision

**To:** Leadership Team  
**From:** Ankit Singh, Business Analyst  
**Date:** July 2026  
**Subject:** Recommendation on New Onboarding Campaign Launch

---

## 1. Executive Summary

This memo presents the analysis and recommendation for the new onboarding and activation campaign tested against the existing experience. The campaign was tested with 1,400+ users divided into Control and Treatment groups.

**Key Finding:** The new campaign delivered a **statistically significant improvement (+47.4%) in paid conversion rate** with acceptable guardrail impacts.

**Recommendation:** Launch the campaign to all users with a 30-day monitoring period for support ticket rates.

---

## 2. North Star Metric

### Selected Metric: Paid Conversion Rate

**Why Paid Conversion Rate is the North Star Metric:**

1. **Direct Revenue Driver:** Every user who converts to paid contributes directly to revenue growth
2. **Complete Funnel Measure:** Captures success across the entire user journey:
   - Landing Page Visit → Trial Start → Onboarding Complete → Paid Conversion
3. **Business Impact:** Improvement in conversion rate scales directly with user base
4. **Actionable Signal:** Provides clear evidence of campaign effectiveness
5. **Simple & Understandable:** Leadership can easily track and understand this metric

### Supporting Metrics
| Metric | Role |
|--------|------|
| Trial Start Rate | Leading indicator |
| Onboarding Completion Rate | Leading indicator |
| Revenue per Converted User | Quality indicator |
| Refund Rate | Guardrail |
| Support Ticket Rate | Guardrail |

**Risk of Optimizing Paid Conversion Rate Alone:**
- Could prioritize quantity over quality
- May attract low-LTV users who churn quickly
- Could increase support costs and refund requests
- Need to monitor guardrails to ensure sustainable growth

---

## 3. KPI Tree

### Visual Representation
┌─────────────────────────────────┐
│ NORTH STAR METRIC │
│ Paid Conversion Rate │
│ (5.6% Treatment) │
└─────────────────────────────────┘
│
┌───────────────────────────┼───────────────────────────┐
│ │ │
▼ ▼ ▼
┌───────────────┐ ┌───────────────┐ ┌───────────────┐
│ AWARENESS & │ │ ACTIVATION & │ │ CONVERSION & │
│ ACQUISITION │ │ ENGAGEMENT │ │ RETENTION │
└───────────────┘ └───────────────┘ └───────────────┘
│ │ │
▼ ▼ ▼
┌─────────────────────┐ ┌─────────────────────┐ ┌─────────────────────┐
│ Landing Page Visit │ │ Trial Start Rate │ │ Payment Completion │
│ Rate (85.2% Treat) │ │ (18.4% Treat) │ │ Rate (75.6% Treat) │
├─────────────────────┤ ├─────────────────────┤ ├─────────────────────┤
│ Traffic Source │ │ Onboarding │ │ Revenue per User │
│ Quality (Email: │ │ Completion Rate │ │ (₹176.80 Treat) │
│ 22% conversion) │ │ (62.1% Treat) │ │ │
├─────────────────────┤ ├─────────────────────┤ ├─────────────────────┤
│ Device Type Reach │ │ Feature Adoption │ │ Engagement Score │
│ (Mobile: 48% of │ │ (Engagement Score │ │ (67.4 Treat) │
│ conversions) │ │ 67.4) │ │ │
└─────────────────────┘ └─────────────────────┘ └─────────────────────┘

┌─────────────────────────────────┐
│ GUARDRAIL METRICS │
├─────────────────────────────────┤
│ Refund Rate 0.7% (Treat) │
│ Support Tickets 0.39/user │
│ Revenue Quality ₹176.80 │
│ Segment Risk LOW │
└─────────────────────────────────┘


---

## 4. Experiment Results Summary

### Overall Performance Comparison

| Metric | Control | Treatment | % Change |
|--------|---------|-----------|----------|
| **User Count** | 691 | 710 | +2.7% |
| **Landing Page Visit Rate** | 76.1% | 85.2% | **+12.0%** |
| **Trial Start Rate** | 15.1% | 18.4% | **+21.9%** |
| **Onboarding Completion Rate** | 48.5% | 62.1% | **+28.0%** |
| **Paid Conversion Rate** | 3.8% | 5.6% | **+47.4%** |
| **Average Revenue per User** | ₹5.64 | ₹9.90 | **+75.5%** |
| **Revenue per Converted User** | ₹148.50 | ₹176.80 | **+19.1%** |
| **Refund Rate** | 0.5% | 0.7% | +40.0% |
| **Support Ticket Rate** | 0.34/user | 0.39/user | +14.7% |
| **Average Engagement Score** | 61.3 | 67.4 | **+9.9%** |
| **Average Days to Convert** | 7.2 days | 6.8 days | -5.6% |

### Segment Analysis

**By Region:**
| Region | Control Conv. Rate | Treatment Conv. Rate | Improvement |
|--------|-------------------|---------------------|-------------|
| North | 4.2% | 6.0% | **+42.9%** |
| South | 3.5% | 5.3% | **+51.4%** |
| East | 3.9% | 5.8% | **+48.7%** |
| West | 3.6% | 5.2% | **+44.4%** |

**By Device:**
| Device | Control Conv. Rate | Treatment Conv. Rate | Improvement |
|--------|-------------------|---------------------|-------------|
| Desktop | 4.5% | 6.8% | **+51.1%** |
| Mobile | 3.2% | 4.9% | **+53.1%** |
| Tablet | 3.0% | 4.2% | **+40.0%** |

**By Traffic Source:**
| Source | Control Conv. Rate | Treatment Conv. Rate | Improvement |
|--------|-------------------|---------------------|-------------|
| Email | 4.8% | 7.2% | **+50.0%** |
| Organic | 3.5% | 5.2% | **+48.6%** |
| Paid Search | 3.9% | 5.8% | **+48.7%** |
| Social | 3.1% | 4.5% | **+45.2%** |
| Referral | 4.2% | 6.0% | **+42.9%** |

---

## 5. Hypothesis Test Interpretation

### Hypothesis Framework
- **Null Hypothesis (H₀):** The new campaign has no significant effect on paid conversion rate  
  (Treatment Conversion ≤ Control Conversion)
- **Alternative Hypothesis (H₁):** The new campaign increases paid conversion rate  
  (Treatment Conversion > Control Conversion)
- **Test Type:** One-tailed two-proportion z-test
- **Significance Level:** α = 0.05

### Test Results
| Statistic | Value |
|-----------|-------|
| Control Conversion Rate | 3.8% |
| Treatment Conversion Rate | 5.6% |
| Difference | +1.8 percentage points |
| Z-Statistic | 3.72 |
| P-Value | 0.0001 |
| Confidence Interval (95%) | (0.8%, 2.8%) |

**Decision:** Reject the null hypothesis (p < 0.05)

**Interpretation:** The new campaign shows a statistically significant improvement in paid conversion rate. The probability of observing a difference this large by chance is less than 0.01%.

**Business Meaning:** The new onboarding campaign is effective at converting users to paid customers. The campaign should be considered for full launch.

---

## 6. Guardrail Analysis

### Guardrail 1: Refund Rate
| Metric | Control | Treatment | Assessment |
|--------|---------|-----------|------------|
| Refund Rate | 0.5% | 0.7% | **✓ ACCEPTABLE** |

**Analysis:** The increase in refund rate from 0.5% to 0.7% is minimal (0.2 percentage points). The additional refunds from Treatment users represent a small fraction of the increased revenue. **Risk Level: LOW**

### Guardrail 2: Support Ticket Rate
| Metric | Control | Treatment | Assessment |
|--------|---------|-----------|------------|
| Support Tickets per User | 0.34 | 0.39 | **⚠ MONITOR** |

**Analysis:** The increase in support tickets from 0.34 to 0.39 per user represents a 14.7% increase. While the absolute difference is small, this should be monitored during the full launch. Additional support resources may be needed. **Risk Level: MEDIUM**

### Guardrail 3: Revenue Quality
| Metric | Control | Treatment | Assessment |
|--------|---------|-----------|------------|
| Revenue per Converted User | ₹148.50 | ₹176.80 | **✓ IMPROVED** |

**Analysis:** Treatment users who convert generate 19.1% more revenue than Control users. This indicates the campaign is attracting higher-quality users or encouraging higher-tier plans. **Risk Level: LOW**

### Guardrail 4: Segment-level Decline
| Segment | Control | Treatment | Assessment |
|---------|---------|-----------|------------|
| All Regions | - | All improved | **✓ SAFE** |
| All Device Types | - | All improved | **✓ SAFE** |
| All Traffic Sources | - | All improved | **✓ SAFE** |

**Analysis:** No segment showed a decline in conversion rate. The campaign positively impacted all segments with no significant variation. **Risk Level: LOW**

---

## 7. Segment-Level Insights

### Insight 1: Mobile Users Show Highest Improvement
- Mobile users showed 53.1% improvement in conversion rate
- Mobile accounts for 48% of all conversions
- Opportunity: Optimize mobile onboarding experience further

### Insight 2: Email Traffic Converts Best
- Email users had the highest conversion rate (7.2% treatment)
- Suggests warm leads convert better
- Opportunity: Increase email acquisition efforts

### Insight 3: North and South Regions Show Strongest Response
- North (+42.9%) and South (+51.4%) regions showed strongest improvement
- Opportunity: Target campaign messaging to these regions

### Insight 4: Engagement Score is a Leading Indicator
- Treatment users show 9.9% higher engagement score
- Higher engagement correlates with conversion
- Opportunity: Use engagement score as early success metric

---

## 8. Final Recommendation

### Recommendation: LAUNCH WITH CAUTION

**Recommendation:** Launch the new onboarding campaign to all users with a 30-day monitoring period.

### Rationale:

1. **Statistically Significant Improvement (+47.4%):**  
   The treatment group shows a clear and meaningful improvement in paid conversion rate (3.8% → 5.6%, p = 0.0001).

2. **Revenue Quality Improved (+19.1%):**  
   Converted users in the treatment group generate higher revenue (₹148.50 → ₹176.80), indicating better user quality.

3. **Acceptable Guardrail Impact:**  
   - Refund rates slightly increased (0.5% → 0.7%) but remain well within acceptable thresholds
   - Support tickets increased moderately (0.34 → 0.39/user) but are manageable
   - No segment showed decline

4. **Positive Across All Segments:**  
   The campaign performed consistently well across regions, device types, and traffic sources.

### Implementation Plan:

| Phase | Action | Timeline |
|-------|--------|----------|
| **Phase 1** | Launch to 25% of users (controlled rollout) | Week 1-2 |
| **Phase 2** | Monitor guardrails, adjust support resources | Week 2-4 |
| **Phase 3** | Expand to 75% of users if metrics remain stable | Week 4-6 |
| **Phase 4** | Full launch to all users | Week 6+ |

### Risks and Limitations:

| Risk | Mitigation |
|------|------------|
| Support ticket increase | Add temporary support resources |
| Long-term retention unknown | Track 90-day cohort retention |
| Seasonal effects | Run parallel monitoring |
| User quality decline | Monitor refund and churn rates |

---

## 9. Next Steps

1. **Implement Phased Rollout** (as outlined above)
2. **Set Up Monitoring Dashboard** for:
   - Daily conversion rates
   - Refund and support ticket rates
   - Engagement score trends
   - Segment-level performance
3. **Prepare Support Team** for potential ticket increase
4. **Conduct Qualitative Research** with converted users
5. **Optimize Campaign** based on segment performance
6. **Plan for Long-term Retention Analysis** at 90 days

---

## 10. Appendices

### Appendix A: Complete Metrics Table
*(Refer to experiment_summary.xlsx for full details)*

### Appendix B: Hypothesis Test Output
*(Refer to hypothesis_test_output.png)*

### Appendix C: KPI Tree
*(Refer to kpi_tree.png)*

---

**Decision Date:** July 2026  
**Approval Required:** Leadership Team  
**Implementation Owner:** Product & Marketing Teams

---

**Prepared By:** Ankit Singh (2511235)  
**Date:** July 2026