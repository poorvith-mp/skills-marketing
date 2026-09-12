---
name: revops
last_reviewed: 2026-09-06
group: Sales handoff
description: >-
  Wire lead scoring, routing, pipeline stages and the marketing-to-sales handoff in the CRM. Use
  when optimizing CRM pipelines, lead routing, or sales operations.
---

# revops

## Core Philosophy
Revenue Operations (RevOps) is the technical infrastructure and governance system that aligns Marketing, Sales, and Customer Success into an unbroken operational pipeline. RevOps eliminates data silos, enforces strict pipeline stage hygiene, automates lead routing, and establishes objective Service Level Agreements (SLAs) between teams. If marketing and sales disagree on lead quality, RevOps fixes the system.

---

## 4-Stage RevOps Architecture

### Stage 1: Lifecycle Stage Definitions & Transition Rules
1. **Standardized Lifecycle Stages**:
   - *Subscriber / Lead*: Known contact in database with no qualification data.
   - *Marketing Qualified Lead (MQL)*: Fits basic ICP criteria and meets explicit behavioral engagement threshold.
   - *Sales Qualified Lead (SQL)*: Verified by SDR/BDR as having budget, authority, need, and buying timeline.
   - *Opportunity*: Active commercial deal with defined product scope and estimated ACV.
   - *Customer*: Signed contract, active billing agreement.
   - *Churned / Closed-Lost*: Formally disqualified or terminated contract.
2. **Transition Criteria**:
   - Every stage shift must have automated, non-subjective criteria. No rep may advance a deal to "Opportunity" without populating: Target Close Date, ACV, Economic Buyer, and Primary Pain Point.

### Stage 2: Lead Scoring & Grading Engine
1. **Two-Dimensional Matrix (Fit vs Engagement)**:
   - *Fit Score (Firmographic / Technographic)*: 0 to 50 points.
     - Company Size (e.g. 50–500 employees = +20 pts).
     - Target Industry (+10 pts).
     - Tech Stack presence (e.g. uses AWS and Kubernetes = +20 pts).
   - *Engagement Score (Behavioral)*: 0 to 50 points (with 30-day decay).
     - Visited pricing page $\ge 2$ times (+15 pts).
     - Downloaded technical whitepaper (+10 pts).
     - Read developer documentation (+15 pts).
2. **Qualification Threshold**:
   - MQL Threshold: Fit Score $\ge 30$ AND Engagement Score $\ge 30$.
   - Route immediately to sales upon crossing threshold.

### Stage 3: Routing Architecture & Inbound SLAs
1. **Lead Routing Logic**:
   - Route inbound leads within 1 minute of form submission.
   - *Round-Robin Rules*: Distribute evenly across active SDRs within geographic territory and company tier.
   - *Fallback Handler*: Automatically assign unrouted leads to Sales Manager if unassigned after 10 minutes.
2. **Strict Inbound SLAs**:
   - Inbound Demo Request: Rep must make first contact within 15 minutes during business hours.
   - Inbound MQL: Rep must make contact within 2 hours.
   - SLA Breach Alerts: Automated Slack notification to Sales Director if lead remains untouched after SLA window.

### Stage 4: Pipeline Hygiene, Velocity & Forecasting
1. **Pipeline Velocity Formula**:
   $$V = \frac{\text{Number of Qualified Opportunities} \times \text{Average Win Rate (\%)} \times \text{Average Deal Size (USD)}}{\text{Sales Cycle Length (Days)}}$$
2. **Hygiene & Stale Deal Rules**:
   - Flag deal as "Stale" if stage does not change in 14 days or close date slips more than twice.
   - Automate mandatory close-lost reason logging with picklist fields (e.g. Lost to Competitor X, Budget Frozen, Missing Feature Y).

---

## Deliverable Format: RevOps Operating Spec (`REVOPS-SPEC.md`)

```markdown
# Revenue Operations Architecture Specification: [Company Name]

## 1. Master Lifecycle Stage Dictionary
| Stage | Definition | Entry Trigger | Mandatory Required Fields |
|---|---|---|---|
| Lead | Form capture / prospect | Web form / import | Email, Company Name |
| MQL | Fit >= 30, Intent >= 30 | Automated score | Company Size, Phone |
| SQL | SDR qualified | SDR discovery call | BANT verified, Problem scope |
| Opportunity | Active buying proposal | Pricing delivered | ACV, Close Date, Buyer Title |
| Closed-Won | Contract signed | DocuSign webhook | Signed MSA, Billing Details |

## 2. Lead Scoring Framework
- **Fit Scoring Factors (Max 50)**:
  - [Factor 1]: [Points]
  - [Factor 2]: [Points]
- **Intent Scoring Factors (Max 50)**:
  - [Action 1]: [Points]
  - [Action 2]: [Points]
- **Decay Rule**: 50% decay on engagement points after 30 days of inactivity.

## 3. SLA & Routing Matrix
- **Inbound Demo Request Response Time**: < 15 minutes
- **MQL Routing Rule**: Round-robin by territory ([Territory 1], [Territory 2])
- **Escalation Notification**: Slack alert to `#sales-alerts` on 30-minute breach

## 4. Key Metrics & Pipeline Health
- **Target Sales Velocity**: [$X/day]
- **Average Win Rate Target**: [e.g. 24%]
- **Average Cycle Length**: [e.g. 42 days]
```

---

## Worked Example: B2B SaaS CRM Automation

- **Challenge**: Sales reps ignored 45% of inbound marketing leads, claiming they were "low quality".
- **Solution**: Built 2-tier scoring in HubSpot. Only leads with verified company domain (>20 employees) and pricing page visits were assigned MQL status. Configured Slack bot alerting reps instantly on MQL creation.
- **Result**: Inbound response time dropped from 4 hours to 12 minutes; MQL-to-SQL conversion increased from 11% to 29%.

---

## Verification Checklist

- [ ] Lifecycle stages have deterministic, objective entry and exit criteria.
- [ ] Lead scoring separates firmographic fit from behavioral intent.
- [ ] Routing rules include a fallback mechanism to prevent orphaned leads.
- [ ] Inbound SLA requires response within 15 minutes for high-intent demo requests.
- [ ] Mandatory CRM fields are enforced at each opportunity stage progression.

---

## Anti-Patterns

- **Subjective MQLs**: Allowing marketing to count any whitepaper download or newsletter subscriber as a qualified sales lead.
- **Sloppy CRM Stages**: Letting deals linger in "Stage 2 Demo" for 180 days without updating the close date.
- **Manual Routing**: Relying on a sales manager to manually assign inbound leads from a spreadsheet.
