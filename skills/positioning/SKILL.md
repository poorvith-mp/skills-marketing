---
name: positioning
group: Foundation
description: >-
  Define category, ICP, differentiators and message hierarchy, then save them as the context file
  every other skill reads. Use when defining category, ICP, differentiators, or message hierarchy.
---

# positioning

## Core Philosophy
Positioning is not copywriting, taglines, or branding fluff. Positioning is the strategic exercise of defining the specific context in which your product wins. Following April Dunford’s *Obviously Awesome* principles, positioning clarifies what your product is, who it is for, why it is uniquely valuable, and why the customer should care—relative to the realistic alternatives they would use if you did not exist.

---

## 5-Step Positioning Architecture

### Step 1: Identify Real Competitive Alternatives
1. **Unpack the Default**:
   - Ask: "What would the customer do if our product vanished tomorrow?"
   - True alternatives are rarely just direct software competitors; they are usually:
     - Internal spreadsheets (Excel/Google Sheets).
     - Manual labor or hiring an intern/contractor.
     - Custom-built internal bash/python scripts.
     - Doing nothing and tolerating the status quo.

### Step 2: Isolate Differentiated Features & Capabilities
1. **Attribute Listing**:
   - List every feature that your product has that the competitive alternatives lack.
   - Filter ruthlessly: Eliminate table-stakes features (e.g. "cloud-based", "secure", "easy to use") that all competitors claim.
2. **Capability Proof**:
   - Every claimed differentiator must have an undeniable technical proof point (e.g. "Rust-based engine executing 100k events/sec locally with zero network egress").

### Step 3: Translate Capabilities into Quantifiable Customer Value
1. **Value Mapping Matrix**:
   - *Feature*: What it is (e.g., Local SQLite cache).
   - *Capability*: What it enables (e.g., Instant offline search without network roundtrips).
   - *Value*: What business outcome it drives (e.g., Saves developer 30 minutes/day and prevents outage downtime).
2. **Value Cluster Grouping**:
   - Group specific value points into 2 or 3 core value themes (e.g., Speed & Ergonomics, Compliance & Privacy, Total Cost of Ownership).

### Step 4: Define the Best-Fit Ideal Customer Profile (ICP)
1. **Firmographic & Technographic Filters**:
   - Identify which subset of accounts cares *desperately* about your unique value:
     - Company size, ARR stage, technology stack dependencies, regulatory constraints.
2. **Trigger Events**:
   - Pinpoint what event forces them into market now (e.g., SOC 2 audit failed, cloud bill doubled, key engineer quit).

### Step 5: Frame Market Category & Context
1. **Category Selection Strategy**:
   - *Head-to-Head*: Take on an established leader in an existing category (e.g. CRM) by proving superiority.
   - *Sub-Segment / Big Fish in Small Pond*: Dominate a specialized niche of an existing category (e.g. CRM for Commercial Real Estate).
   - *New Category*: Create a novel category when existing mental models completely fail to describe the solution.

---

## Deliverable Format: The Master Positioning Canvas (`POSITIONING.md`)

```markdown
# Product Positioning Document: [Product Name]

## 1. Market Context & Status Quo
- **Category Name**: [Defined category]
- **Real Alternatives**: [Spreadsheets, manual process, Incumbent X]
- **Status Quo Flaw**: [Why the current way is breaking down]

## 2. Core Value Pillars
| Unique Feature | Customer Capability | Business Value Outcome |
|---|---|---|
| [Feature A] | [Capability A] | [Saves X hours / cuts Y cost] |
| [Feature B] | [Capability B] | [Eliminates risk Z] |

## 3. Ideal Customer Profile (ICP)
- **Target Company Profile**: [Size, industry, tech stack]
- **Economic Buyer**: [Title / Role]
- **Primary Pain Trigger**: [Immediate catalyst for buying]

## 4. Message Hierarchy & Positioning Statement
- **For** [Target ICP],
- **Who** [Suffers from specific pain point],
- **[Product Name] is a** [Category descriptor],
- **That** [Delivers core primary value].
- **Unlike** [Primary competitive alternative],
- **Our product** [Key differentiated capability].
```

---

## Worked Example: High-Performance Database Migration Tool

- **Competitive Alternative**: Raw flyway/liquibase scripts or ORM migrations (`prisma migrate`, `alembic`).
- **Unique Capabilities**: Instant dry-run emulation in a local ephemeral container; automatic detection of table-locking DDL operations.
- **Value**: Zero-downtime schema migrations; eliminates 2 AM production outages.
- **Target ICP**: Post-Series A engineering teams (30–150 devs) running PostgreSQL on AWS RDS deploying >5 times per day.
- **Category Framing**: Sub-segment of database DevOps: "Zero-Downtime Migration Safety Platform for Postgres".

---

## Verification Checklist

- [ ] Alternatives list includes non-software status quo (spreadsheets, manual processes).
- [ ] Differentiators are backed by verifiable technical capabilities, not subjective adjectives.
- [ ] Value points quantify business impact (cost, time, risk reduction).
- [ ] ICP includes firmographics, tech stack prerequisites, and buying trigger events.
- [ ] One-sentence positioning statement passes the "replace with competitor name" test (if competitor can say it, rewrite it).

---

## Anti-Patterns

- **Adjective Soup**: Relying on "intuitive", "scalable", "powerful", or "AI-driven" without defining concrete capabilities.
- **Universal Appeal Fallacy**: Claiming "anyone who writes code" or "all businesses" is your target customer.
- **Feature-Led Messaging**: Pitching architectural details without explaining the resulting business outcome.
