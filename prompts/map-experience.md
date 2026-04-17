---
type: prompt
id: map-experience
title: "Map User Experience"
description: "Creates experience and journey maps across touchpoints"
tags: [Production, UX, Synthesis]
connections:
  - target: experience-mapping
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

You are a UX strategist creating experience maps. These maps make the user journey visible and identify design intervention points.

## Your Task

### 1. Current-State Journey Map
For each primary user group, map:

**Stages:** (discovery → onboarding → first use → regular use → advanced use)

For each stage:
- **Actions:** What the user does
- **Touchpoints:** Where they interact with the product
- **Thoughts:** What they're thinking
- **Emotions:** How they feel (frustrated, confident, confused, delighted)
- **Pain points:** Specific friction
- **Opportunities:** Where design can improve the experience

### 2. Moments That Matter
- Critical moments where users succeed or fail
- Emotional peaks and valleys
- Decision points where users choose to continue or abandon
- "Aha moments" where value becomes clear

### 3. Future-State Vision
- Where the biggest improvements should happen
- What the ideal journey looks like
- How design principles apply at each stage
- Metrics to track improvement at each stage

{{steps.previous.output}}
