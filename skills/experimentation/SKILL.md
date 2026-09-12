---
name: experimentation
last_reviewed: 2026-09-06
group: Measurement
description: >-
  Design A/B tests, set sample size and duration, read results honestly, and run the backlog. Use
  when running A/B split tests, sample sizing, or conversion experiments.
---

# Experimentation

Growth experimentation is the scientific method applied to software conversion funnels. A/B testing fails when teams launch underpowered tests, declare premature victory without statistical significance, or test trivial cosmetic changes. A professional experimentation practice requires statistical sample-size power calculations, structured hypothesis backlogs (ICE scoring), and disciplined holdout verification.

## 1. Statistical Foundations & Test Sizing
Before launching an experiment, calculate mandatory sample size based on statistical parameters:
- **Minimum Detectable Effect (MDE)**: The smallest relative conversion lift you care about detecting (e.g. 10% relative lift).
- **Statistical Power ($1 - \beta$)**: Standard baseline is **80%** (20% false negative rate).
- **Statistical Significance ($\alpha$)**: Standard baseline is **95%** ($p < 0.05$, 5% false positive rate).
- **Sample Size Formulation**:
  $$n = \frac{2 \times (Z_{\alpha/2} + Z_{\beta})^2 \times p \times (1 - p)}{\delta^2}$$
  - $p$: Baseline conversion rate; $\delta$: Absolute detectable effect ($p \times \text{MDE}$).
- *Runtime Constraint Rule*: If your monthly traffic requires more than 4 weeks to reach statistical power, the test is underpowered; choose a higher-traffic surface or test a bolder structural variation.

## 2. The ICE Hypothesis Backlog Prioritization
Score candidate experiments across three dimensions (1–10 scale):
- **Impact**: How much will conversion increase if this hypothesis is correct? (10 = Core checkout page; 1 = Footer link).
- **Confidence**: What empirical evidence supports this hypothesis? (10 = Directly backed by customer interview data and analytics drop-off; 1 = Pure founder intuition).
- **Ease**: How quickly can engineering and design ship this test? (10 = Simple copy change in CMS; 1 = Requires new backend architecture).
- **ICE Score**:
  $$\text{ICE Score} = \frac{\text{Impact} + \text{Confidence} + \text{Ease}}{3}$$

## 3. The 4-Part Experiment Design Brief
Every test must be documented prior to deployment:
1. **Observation & Data**: "Analytics show 68% of users drop off at Step 2 of registration where phone number is requested."
2. **Hypothesis**: "Removing the optional phone number field will reduce perceived privacy friction and increase signup completion by 15%."
3. **Primary Metric**: Signup completion rate (`signup_completed / registration_page_views`).
4. **Guardrail Metric**: Downstream activation rate (ensuring quality of signups does not degrade).

## 4. Analyzing Test Results Honestly
- **Never peek and stop early**: Checking a test daily and stopping when $p < 0.05$ inflates false positive rates to >30%. Fix the sample size in advance and run the test for full business cycles (minimum 2 full weeks to smooth weekday/weekend variance).
- **Inconclusive Results**: A flat test ($p > 0.05$) is not a failure; it proves the tested variable does not constrain conversion. Revert to control and archive the learning.

## Critical Rules
1. Never declare a winning variation without reaching 95% statistical significance and minimum pre-calculated sample size.
2. Every experiment must run for at least two full 7-day calendar cycles to account for day-of-week seasonality.
3. Every test must track a secondary guardrail metric to prevent optimizing for clicks at the expense of retention.

## Verification Checklist
- [ ] Sample size and test duration calculated prior to launching test variations.
- [ ] Test instrumented to run across at least 2 full weekly business cycles.
- [ ] Primary conversion event and secondary guardrail metrics established in analytics.
- [ ] Experiment documented in central repository with hypothesis and ICE score.
- [ ] Traffic split (50/50) verified evenly distributed without session leakage.

## Anti-Patterns
- NEVER stop a test early because results look good on Day 3; early variance regression to the mean will wipe out illusory gains.
- NEVER test minor button color shades when core value proposition copy remains unvalidated.
- NEVER run multiple overlapping tests on the same user journey without isolating interaction effects.
