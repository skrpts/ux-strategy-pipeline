---
type: prompt
id: frame-problem
title: "Frame Problem"
description: "Defines the problem space from context, users, and business goals"
tags: [Production, UX, Strategy]
connections:
  - target: problem-framing
    type: derived_from
inputs:
  product_context:
    label: "Product Context"
    description: "Your product, its current state, and what it does"
    example: "B2B SaaS analytics dashboard, 2 years old, 500 enterprise customers"
    required: true
    type: text
  target_users:
    label: "Target Users"
    description: "Primary user groups"
    example: "Data analysts and business managers who need weekly performance reports"
    required: true
    type: text
  competitors:
    label: "Competitors"
    description: "Key competitors to analyse"
    example: "Looker, Tableau, Metabase, Mode"
    required: false
    type: text
  business_goals:
    label: "Business Goals"
    description: "What the business needs from this UX work"
    example: "Reduce time-to-insight from 30 minutes to under 5 minutes, improve NPS from 32 to 50"
    required: false
    type: text
---

You are a UX strategist defining the problem space for a design initiative.

## Product Context
{{input.product_context}}

## Target Users
{{input.target_users}}

## Competitors
{{input.competitors}}

## Business Goals
{{input.business_goals}}

## Your Task

### 1. Problem Definition
- **Core problem statement** (one sentence)
- **Who is affected** and how
- **Current impact** (quantified where possible)
- **Root causes** (not symptoms)

### 2. User Landscape
- Primary user groups with distinct needs
- Jobs-to-be-done for each group
- Current pain points by group
- Unmet needs and latent desires

### 3. Business Context
- How the UX problem connects to business metrics
- Constraints (technical, organisational, timeline, budget)
- Stakeholder priorities and potential conflicts
- Success metrics for the initiative

### 4. Opportunity Space
- Where the biggest gaps exist between user needs and current experience
- Areas where competitors are weak
- Emerging user expectations from adjacent products
- Innovation opportunities (not just fixing what's broken)

### 5. Problem Boundaries
- What's in scope and out of scope
- Dependencies on other teams or systems
- Known unknowns that need research
