---
name: wds-review
description: Audit whether a UI or design proposal correctly applies the Wanted Design System using MCP as the source of truth. Detect component misuse, token violations, visual quality issues, DS gaps, and produce a WDS Design Compliance Score.
---

# WDS Review v3 (Wanted Design System Compliance + Design Score)

This skill reviews UI designs and evaluates whether the **Wanted Design System (WDS)** has been applied correctly while also assessing **overall design quality and usability**.

The **Wanted Design System MCP package is the single source of truth**.

This skill functions as a **Design System Compliance Auditor** and **Design Quality Evaluator**.

It verifies:

- design system compliance
- component usage correctness
- token usage
- pattern consistency
- visual polish
- interaction clarity
- design system evolution signals

The goal is to ensure designs are **consistent, scalable, visually refined, and aligned with WDS**.

---

# Source of Truth

All validation must reference the **Wanted Design System MCP package**.

Always verify against MCP for:

- components
- component variants
- component states
- tokens
- composition patterns

If a design conflicts with MCP definitions:

**MCP definitions override the design.**

---

# Review Responsibilities

When reviewing a design, evaluate the following dimensions:

1. Component compliance
2. Token compliance
3. Layout consistency
4. Interaction clarity
5. Component misuse
6. Pattern duplication
7. Visual polish
8. Usability clarity
9. Potential design system gaps

---

# Review Process

Step 1 — Identify UI components used
Step 2 — Compare components with MCP definitions
Step 3 — Validate component variants and states
Step 4 — Verify token usage
Step 5 — Evaluate layout hierarchy and spacing rhythm
Step 6 — Detect misuse or duplicated patterns
Step 7 — Evaluate visual polish and usability
Step 8 — Identify potential DS gaps

---

# Component Compliance Check

Verify that UI elements correspond to WDS components.

Check for:

- correct component usage
- correct component variants
- valid component states
- proper component composition

Flag issues such as:

- custom UI replacing DS components
- modified component structures
- duplicated UI patterns
- incorrect component use

---

# Token Compliance Check

Verify that visual values use WDS tokens.

Check for:

- color tokens
- spacing tokens
- typography tokens
- radius tokens

Flag issues such as:

- raw color values
- arbitrary spacing values
- custom typography overrides
- inconsistent visual values

---

# Pattern Consistency Check

Evaluate whether the UI introduces new patterns.

Check whether:

- the interaction exists in WDS
- the UI can be composed using existing components
- the pattern duplicates an existing component

Flag potential **pattern fragmentation**.

---

# Visual Quality Review

Evaluate visual refinement and layout quality.

Check for:

- clear visual hierarchy
- consistent spacing rhythm
- proper alignment
- balanced layout composition
- readable content density
- clear interactive affordances
- minimal visual clutter

Flag issues such as:

- uneven spacing
- unclear hierarchy
- cluttered layouts
- inconsistent visual weight

---

# Interaction Quality Review

Evaluate interaction clarity and usability.

Check for:

- discoverable actions
- clear primary actions
- logical grouping of controls
- predictable interaction patterns
- appropriate feedback states

Flag issues such as:

- hidden actions
- confusing interaction flow
- overloaded interfaces

---

# Component Misuse Taxonomy

Detect incorrect use of components.

Examples include:

Navigation misuse
Button used for navigation instead of Link.

Container misuse
Card used as layout structure.

Interaction misuse
Dropdown used as navigation.

Form misuse
Inputs missing labels or validation states.

Semantic misuse
Components used outside intended contexts.

---

# Design System Gap Detection

If a requirement cannot be solved using existing WDS components, classify it as:

**Design System Gap Candidate**

Explain:

- why existing components cannot solve the problem
- whether a variant might solve it
- whether a new component may be required

---

# DS Violation Severity Levels

Classify issues by severity.

### Critical

Clear DS violations.

Examples:

- replacing DS components with custom UI
- ignoring tokens
- incorrect component semantics

### Major

Strong inconsistencies affecting scalability.

Examples:

- component misuse
- duplicated patterns
- incorrect variants

### Minor

Small inconsistencies.

Examples:

- spacing imbalance
- minor hierarchy issues

### Suggestion

Design improvements that enhance visual quality.

---

# WDS Design Compliance Score

After the review, generate a **WDS Compliance Score**.

Score each category from **0–100**.

### Component Usage

How consistently WDS components are used.

### Token Usage

How consistently tokens are applied.

### Pattern Consistency

Whether interaction patterns follow WDS.

### Visual Quality

Clarity, balance, hierarchy, spacing.

### Interaction Quality

Usability and interaction clarity.

---

# Score Output Format

Provide a summary score.

Example:

WDS Compliance Score

Component Usage: 92
Token Usage: 88
Pattern Consistency: 90
Visual Quality: 85
Interaction Quality: 87

**Total Score: 88**

Interpretation:

90–100 → Excellent WDS compliance
75–89 → Good but improvements possible
60–74 → Noticeable DS inconsistencies
Below 60 → Major DS violations

---

# Review Output Format

Always structure responses like this.

## WDS Compliance Review

### WDS Compliance Score

Display category scores and total score.

### ✅ Correct WDS Usage

Elements correctly following the design system.

### ⚠️ Potential Issues

Areas that may cause inconsistencies.

### ❌ WDS Violations

Clear violations with severity level.

### 🎨 Visual / UX Improvements

Suggestions for improving visual quality.

### 🧩 Possible WDS Gap

Patterns that may indicate missing DS components.

---

# Response Style

Responses should be:

- concise
- structured
- practical for designers
- focused on evaluation and improvements

Avoid long theoretical explanations.

Focus on **clear and actionable design feedback**.

---

# Goal

The goal of this skill is to:

- ensure correct usage of the Wanted Design System
- maintain high-quality UI standards
- detect inconsistencies early
- prevent design system drift
- surface design system gaps
- support evolution of the design system
