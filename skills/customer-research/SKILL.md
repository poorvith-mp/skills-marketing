---
name: customer-research
group: Foundation
description: >-
  Mine interviews, tickets, reviews and communities for the exact words customers use; output
  personas and JTBD. Use when mining customer voice, interview transcripts, or user pains.
---

# Customer Research

Customer research is extracting the unvarnished voice of the customer (VOC) to guide product development and marketing messaging. High-impact research uncovers Jobs to Be Done (JTBD), identifies switching triggers, isolates exact pain vocabulary, and turns qualitative interviews into structured persona dossiers.

## 1. The Jobs to Be Done (JTBD) Interview Framework
Customers do not buy products; they "hire" them to make progress in a specific life or operational situation:
- **The 4 Forces of Customer Progress (Bob Moesta Framework)**:
  1. *Push of the Current Situation*: The pain, frustration, or inefficiency of the existing solution that makes staying intolerable.
  2. *Pull of the New Solution*: The attractive promise of the new product and how it will improve their operational reality.
  3. *Anxiety of the Unknown*: Fear that the new solution will break, fail to integrate, or cost too much time to learn.
  4. *Habit & Inertia*: Comfort with the legacy routine and reluctance to change existing muscle memory.

## 2. The 5 Golden Interview Questions
When conducting customer discovery interviews (20–30 minutes), never ask hypothetical questions ("Would you buy X?"). Ask about past behaviors:
1. *"Take me back to the day you first started looking for a solution like this. What happened that day that made you say 'I need to fix this'?"* (Identifies the switching trigger).
2. *"What other solutions did you try or consider before choosing us, and why did you rule them out?"* (Identifies true competitors and trade-offs).
3. *"What was the hardest part about getting set up or convincing your team to use this?"* (Identifies onboarding and adoption friction).
4. *"What can you do now that you couldn't do before?"* (Isolates the core value proposition in the customer's exact words).
5. *"If you could no longer use this tomorrow, what would you replace it with?"* (Identifies mission-critical dependencies).

## 3. Review Mining & Digital Watering Hole Extraction
Mine unprompted customer discussions across public channels (Reddit, G2 reviews, Discord servers, support tickets):
- **Pain Vocabulary Mining**: Copy verbatim phrases customers use to describe their frustration into a raw VOC spreadsheet.
- **Feature Gap Identification**: Categorize complaints about incumbent competitors into actionable product roadmap inputs.
- *Synthesis Rule*: When 5 distinct customers use the exact same phrase to describe their problem, adopt that exact phrase as your landing page headline.

## 4. Structured Customer Persona Dossier
Synthesize findings into actionable profiles, not cartoon demographic avatars:
- **Role & Constraints**: Senior Backend Engineer; budget authority up to $5,000/yr; constrained by SOC 2 compliance and tight sprint deadlines.
- **Core Job to Be Done**: "Quickly deploy reliable background job queues in TypeScript without managing self-hosted Redis infrastructure."
- **Objections & Hesitations**: "Worried about API rate limits and bill shock from usage-based pricing."

## Critical Rules
1. Never ask customers what features you should build; ask what problems they are experiencing and what progress they are trying to make.
2. Record and transcribe customer interviews to capture their exact vocabulary word-for-word.
3. Disregard hypothetical customer feedback ("I would definitely pay $50 for that"); only count verified past actions and paid commitments.

## Verification Checklist
- [ ] Qualitative interviews conducted with at least 5 representative users from the target ICP.
- [ ] Switching triggers and the 4 Forces of Progress documented.
- [ ] Verbatim Voice of Customer (VOC) phrases extracted and tagged in a central repository.
- [ ] Personas defined by jobs-to-be-done and operational constraints rather than demographics.
- [ ] Findings synthesized and shared directly with product engineering and copywriting teams.

## Anti-Patterns
- NEVER lead the witness during interviews with suggestive questions ("Don't you think our UI is much cleaner?").
- NEVER build buyer personas based on internal company assumptions without direct customer validation.
- NEVER conduct research once and shelve it; interview at least 2 churned or won customers every month.
