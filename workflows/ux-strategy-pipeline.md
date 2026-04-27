---
type: workflow
id: ux-strategy-pipeline
title: UX Strategy Pipeline
description: "Define the problem space, analyse competitors, generate design principles, map experiences, and produce strategic recommendations"
tags: [Production, Customer-Facing, UX, Strategy, Analysis]
connections:
  - target: problem-framing
    type: uses
  - target: competitive-ux-analysis
    type: uses
  - target: design-principles-generation
    type: uses
  - target: experience-mapping
    type: uses
  - target: strategic-recommendations
    type: uses
  - target: language-polish
    type: uses
  - target: consistency-check
    type: uses
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "15-25 minutes"
  trigger: manual
output_step: "language-polish"
composite_steps:
  - "problem-framing"
  - "competitive-ux-analysis"
  - "design-principles-generation"
  - "experience-mapping"
  - "strategic-recommendations"
  - "language-polish"
  - "consistency-check"
execution:
  - skill: "problem-framing"
    prompt: "frame-problem"
    step_type: "synthesis"
  - skill: "competitive-ux-analysis"
    prompt: "analyse-competitive-ux"
    step_type: "synthesis"
  - skill: "design-principles-generation"
    prompt: "generate-design-principles"
    step_type: "generation"
  - skill: "experience-mapping"
    prompt: "map-experience"
    step_type: "generation"
  - skill: "strategic-recommendations"
    prompt: "recommend-strategy"
    step_type: "synthesis"
  - skill: "language-polish"
    prompt: "polish-language"
    step_type: "content"
  - parallel:
    - skill: "consistency-check"
      prompt: "check-consistency"
      step_type: "review"
---

## Overview

This workflow produces a complete UX strategy from problem definition through strategic recommendations. It frames the problem, analyses the competitive landscape, generates design principles, maps user experiences, and produces a prioritised roadmap.

## Pipeline Stages

### Stage 1: Problem Framing

**Input:** Product context, target users, competitors, business goals

Invoke the **problem-framing** skill to define the problem space, user landscape, business context, and opportunity space.

**Output:** Problem definition with boundaries and success metrics.

### Stage 2: Competitive UX Analysis

**Input:** Problem framing from Stage 1

Invoke the **competitive-ux-analysis** skill to analyse competitors' UX approaches, strengths, weaknesses, and identify strategic gaps.

**Output:** Competitive matrix with opportunity identification.

### Stage 3: Design Principles

**Input:** Problem framing and competitive analysis

Invoke the **design-principles-generation** skill to produce 5-7 actionable, specific design principles.

**Output:** Design principles with rationale, examples, tensions, and tests.

### Stage 4: Experience Mapping

**Input:** All previous analysis

Invoke the **experience-mapping** skill to create current-state journey maps, identify moments that matter, and envision the future state.

**Output:** Journey maps with emotional curves and intervention opportunities.

### Stage 5: Strategic Recommendations

**Input:** Complete analysis from all stages

Invoke the **strategic-recommendations** skill to produce a prioritised roadmap with initiatives, phases, metrics, and risk mitigations.

**Output:** Strategic recommendations with phased roadmap.

### Stage 6: Language Polish

Invoke **language-polish** for final cleanup.

### Stage 7: Consistency Check (Parallel)

Invoke **consistency-check** to verify principles, maps, and recommendations align.

## Error Handling

- If no competitors are provided, the competitive analysis focuses on general UX best practices in the space
- If business goals are vague, recommendations prioritise user impact over business metrics

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.product_context}}` | Yes | Your product and its current state | `B2B SaaS analytics dashboard, 500 customers` |
| `{{input.target_users}}` | Yes | Primary user groups | `Data analysts and business managers` |
| `{{input.competitors}}` | No | Key competitors | `Looker, Tableau, Metabase` |
| `{{input.business_goals}}` | No | Business objectives | `Reduce time-to-insight, improve NPS` |

## Outputs

| Name | Description |
|------|-------------|
| Problem definition | Problem space, user landscape, opportunity areas |
| Competitive analysis | UX strengths, weaknesses, and gaps across competitors |
| Design principles | 5-7 actionable principles for the initiative |
| Experience maps | Current-state journey maps and future-state vision |
| Strategic recommendations | Prioritised roadmap with phases and metrics |

## Setup

1. No external services required.
2. The more context you provide about your product, users, and competitors, the sharper the strategy.

## Provider Notes

- All stages benefit from stronger models — strategy requires nuanced synthesis.
- The five sequential stages produce a comprehensive deliverable.

## Example Input

```
Product Context: "B2B SaaS analytics dashboard, 2 years old, 500 enterprise customers. Current product lets users build custom dashboards, write SQL queries, and schedule reports. Good adoption for power users but low engagement from business managers who need insights without writing SQL."
Target Users: "Data analysts who build dashboards and write queries (power users, 20% of users, high engagement). Business managers who consume reports and need quick answers (80% of users, low engagement, high churn risk)."
Competitors: "Looker (strong governance, complex setup), Tableau (powerful visualisation, steep learning curve), Metabase (simple, limited for power users), Mode (good for analysts, weak for business users)"
Business Goals: "Reduce time-to-insight from 30 minutes to under 5 minutes for business managers. Improve NPS from 32 to 50. Reduce churn for business manager segment from 18% to under 10%."
```
