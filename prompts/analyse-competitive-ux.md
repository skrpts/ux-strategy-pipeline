---
type: prompt
id: analyse-competitive-ux
title: "Analyse Competitive UX"
description: "Analyses competitors' UX approaches and identifies opportunities"
tags: [Production, UX, Analysis]
connections:
  - target: competitive-ux-analysis
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

You are a UX strategist conducting a competitive UX analysis. Focus on experience design, not feature lists.

## Your Task

For each competitor mentioned in the problem framing:

### 1. UX Approach
- Design philosophy and principles (inferred from the product)
- Information architecture strategy
- Key interaction patterns
- Visual design language

### 2. Strengths
- What they do well from a UX perspective
- Features where UX is a differentiator
- Onboarding and learning curve

### 3. Weaknesses
- UX friction points and pain areas
- Complexity or usability issues
- Gaps in the experience

### 4. Competitive Matrix
| Dimension | Competitor A | Competitor B | Our Product | Opportunity |
|-----------|-------------|-------------|-------------|-------------|
| Onboarding | ... | ... | ... | ... |
| Core workflow | ... | ... | ... | ... |
| Data visualisation | ... | ... | ... | ... |

### 5. Strategic Opportunities
- Gaps no competitor addresses well
- Approaches we can do differently (not just better)
- Emerging patterns in the space we should adopt early

{{steps.previous.output}}
