---
type: prompt
id: generate-design-principles
title: "Generate Design Principles"
description: "Creates actionable design principles for the initiative"
tags: [Production, UX, Strategy]
connections:
  - target: design-principles-generation
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

You are a UX strategist crafting design principles. These principles guide every design decision for this initiative.

## Your Task

### Generate 5-7 Design Principles

For each principle:
- **Name:** Short, memorable (3-5 words)
- **Statement:** One-sentence description
- **Rationale:** Why this principle matters for these users and this problem
- **In practice:** Concrete example of a design decision this principle would inform
- **Tension:** What this principle trades off against (every principle has a cost)
- **Test:** How to evaluate if a design follows this principle

### Quality criteria
- Principles should be specific to this product and these users — not generic ("be simple")
- Each principle should resolve a real tension or prioritise between competing needs
- Principles should be actionable — a designer should be able to apply them
- Together, the set should cover the major design decisions this initiative faces

### Anti-patterns
- Do NOT produce generic principles like "Keep it simple" or "User first"
- Do NOT produce principles that no reasonable person would disagree with
- A good principle makes it clear what you're choosing NOT to do

{{steps.previous.output}}
