---
name: article-writing
group: Content
description: Write the piece: search-intent structure, keyword headings, internal links and schema. For prose voice, see writing-taste. Use when drafting in-depth articles, tutorials, or essays.
---

# Article Writing

Technical article writing is search-intent satisfaction and authority building, not keyword-stuffed SEO filler. High-ranking technical articles provide immediate answers to user queries, maintain clean structural hierarchies, include original code/data illustrations, and eliminate AI writing tells.

## 1. Search-Intent Decomposition & Article Architecture
Before writing a single sentence, classify the searcher's intent:
- **Informational / Conceptual**: Seeking understanding ("How does Raft consensus work?"). Requires architectural diagrams, historical context, and mental models.
- **Procedural / How-To**: Seeking execution ("How to configure Redis cluster in Docker"). Requires step-by-step terminal commands, configuration snippets, and error mitigation.
- **Commercial / Comparative**: Seeking a purchasing or architectural decision ("Kafka vs RabbitMQ"). Requires benchmark tables, tradeoff criteria, and decision trees.

## 2. The Structural Layout Template

```markdown
# [Clear, Search-Intent Focused Title]

[Direct 2-sentence answer summarizing the solution and core takeaway]

## 1. The Core Problem & Conceptual Architecture
[Explain why this challenge exists, what breaks in naive implementations, and provide a diagram]

## 2. Step-by-Step Implementation Guide
### Step 1: Environment & Prerequisites
```bash
# Executable command
```
### Step 2: Core Configuration
```typescript
// Complete, working code block with error handling
```

## 3. Production Edge Cases & Performance Trade-offs
[Detail memory limits, failure states, latency implications, and real-world benchmarks]

## 4. Key Takeaways & Decision Matrix
| Option / Parameter | Best For | Trade-off / Limitation |
|---|---|---|
| Approach A | Low latency | Higher memory usage |
| Approach B | Simplicity | Limited throughput |
```

## 3. Technical Credibility & Code Quality Standards
- **Runnable Code**: Every code block must be syntactically valid and tested against named software versions.
- **Information Gain**: Never write an article that merely summarizes the top 3 Google search results. Add original benchmarking, failure post-mortems, or proprietary production data.
- **Style Rules**: Use second-person ("you") and present tense; eliminate fluff introductions ("In today's fast-paced digital world..."); lead immediately with the problem and solution.

## 4. Internal Linking & Topic Cluster Integration
- Link out to 2–3 sibling articles within the same thematic cluster to pass domain authority.
- Anchor text must describe the target page specifically (e.g. "review our [PostgreSQL indexing guide](/db-indexing)"), never generic phrases like "click here".

## Critical Rules
1. Lead with the answer or executable code block within the first 150 words of the article.
2. All code snippets must include language syntax tags (` ```python `, ` ```bash `) and explicit dependency requirements.
3. Eliminate passive voice and corporate buzzwords; state facts, measurements, and trade-offs directly.

## Verification Checklist
- [ ] H1 and H2 headings reflect search queries and follow strict markdown hierarchy.
- [ ] Code snippets verified runnable with versions stated.
- [ ] Article contains original data, benchmark comparisons, or practical examples.
- [ ] Internal links connect to relevant cluster documentation.
- [ ] Anti-AI writing sweep completed (zero robotic transitions, hedging, or fluff).

## Anti-Patterns
- NEVER write long introductory fluff explaining why a topic is important before answering the query.
- NEVER publish untested pseudo-code that fails when copied into a developer's terminal.
- NEVER hide the direct answer behind a wall of marketing preamble.
