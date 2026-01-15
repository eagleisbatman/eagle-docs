---
name: prioritization-framework-design
description: Create professional prioritization framework documents as HTML. Includes RICE scoring, MoSCoW method, ICE framework, Value/Effort matrix, Kano model, and weighted scoring. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Use when user requests prioritization framework, RICE analysis, feature scoring, backlog prioritization, or decision matrix.
---

# Prioritization Framework Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional prioritization framework documents as self-contained HTML files. Supports multiple prioritization methodologies with visual scoring systems. Optimized for desktop/laptop viewing (1024px+).

## Theme Support

Before generating, check for user preferences:

1. **Config file**: Look for `.eagle-docs.yaml` in project root
2. **Runtime prompt**: Ask user if no config exists

Available themes:
- **Brutalist** — Bold black-and-white, data-focused
- **Material 3** — Rounded corners, friendly visuals
- **Cupertino** — Apple-style, refined look
- **Modern Minimal** — Clean, contemporary

See `shared/DESIGN-SYSTEM.md` for complete theme specifications.

## Supported Frameworks

### 1. RICE Scoring
- **R**each: How many users affected per quarter
- **I**mpact: Score 0.25 (minimal) to 3 (massive)
- **C**onfidence: 100% (high) to 50% (low)
- **E**ffort: Person-months required

Formula: `RICE Score = (Reach × Impact × Confidence) / Effort`

### 2. MoSCoW Method
- **M**ust have: Critical, non-negotiable
- **S**hould have: Important but not critical
- **C**ould have: Nice to have
- **W**on't have: Out of scope for now

### 3. ICE Scoring
- **I**mpact: 1-10 scale
- **C**onfidence: 1-10 scale
- **E**ase: 1-10 scale (inverse of effort)

Formula: `ICE Score = (Impact + Confidence + Ease) / 3`

### 4. Value vs Effort Matrix
- 2×2 quadrant visualization
- Quick Wins (High Value, Low Effort)
- Big Bets (High Value, High Effort)
- Fill-ins (Low Value, Low Effort)
- Avoid (Low Value, High Effort)

### 5. Kano Model
- Must-haves (Basic expectations)
- Performance (Linear satisfaction)
- Delighters (Unexpected value)
- Indifferent (No impact)
- Reverse (Causes dissatisfaction)

### 6. Weighted Scoring
- Custom criteria with weights
- Normalized scoring
- Weighted total calculation

## Document Structure

1. **Executive Summary** - Top priorities, methodology used
2. **Methodology Overview** - Framework explanation
3. **Scoring Criteria** - Definitions and scales
4. **Feature/Initiative List** - Items being prioritized
5. **Scoring Matrix** - Full scoring breakdown
6. **Priority Ranking** - Ordered results
7. **Visualization** - Charts and matrices
8. **Recommendations** - Action items
9. **Appendix** - Raw data, assumptions

## Key Components

### RICE Score Card
```css
.rice-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    margin-bottom: 24px;
    box-shadow: var(--shadow-md);
}

.rice-header {
    background: var(--color-primary);
    color: white;
    padding: 20px 24px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.rice-title {
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 700;
}

.rice-score {
    font-family: var(--font-mono);
    font-size: 32px;
    font-weight: 700;
}

.rice-body {
    padding: 24px;
}

.rice-metrics {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
    margin-bottom: 20px;
}

.rice-metric {
    text-align: center;
    padding: 16px;
    background: var(--color-surface-variant, #f5f5f5);
    border-radius: var(--radius-sm);
}

.metric-value {
    font-family: var(--font-mono);
    font-size: 24px;
    font-weight: 700;
    color: var(--color-primary);
}

.metric-label {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--color-text-muted);
    margin-top: 4px;
}

.rice-formula {
    font-family: var(--font-mono);
    font-size: 14px;
    color: var(--color-text-muted);
    text-align: center;
    padding: 12px;
    background: var(--color-surface-variant, #f5f5f5);
    border-radius: var(--radius-sm);
}
```

### MoSCoW Category
```css
.moscow-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 24px;
}

.moscow-category {
    border: var(--border-width) solid var(--color-border);
    border-radius: var(--radius-md);
    overflow: hidden;
}

.moscow-header {
    padding: 16px 20px;
    font-family: var(--font-heading);
    font-size: 16px;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 12px;
}

.moscow-must { background: #FEE2E2; color: #991B1B; }
.moscow-should { background: #FEF3C7; color: #92400E; }
.moscow-could { background: #DBEAFE; color: #1E40AF; }
.moscow-wont { background: #F3F4F6; color: #6B7280; }

.moscow-items {
    padding: 16px 20px;
    background: var(--color-surface);
}

.moscow-item {
    padding: 12px 0;
    border-bottom: 1px solid var(--color-border);
    font-size: 14px;
}

.moscow-item:last-child {
    border-bottom: none;
}
```

### Value/Effort Matrix
```css
.matrix-container {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    padding: 40px;
    margin: 32px 0;
}

.matrix-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    gap: 4px;
    height: 400px;
    position: relative;
}

.matrix-quadrant {
    padding: 20px;
    display: flex;
    flex-direction: column;
}

.quadrant-quick-wins {
    background: #D1FAE5;
    border-radius: var(--radius-md) 0 0 0;
}

.quadrant-big-bets {
    background: #DBEAFE;
    border-radius: 0 var(--radius-md) 0 0;
}

.quadrant-fill-ins {
    background: #FEF3C7;
    border-radius: 0 0 0 var(--radius-md);
}

.quadrant-avoid {
    background: #FEE2E2;
    border-radius: 0 0 var(--radius-md) 0;
}

.quadrant-label {
    font-family: var(--font-heading);
    font-size: 14px;
    font-weight: 700;
    margin-bottom: 12px;
}

.quadrant-items {
    font-size: 13px;
    line-height: 1.8;
}

.matrix-axis-y {
    position: absolute;
    left: -60px;
    top: 50%;
    transform: rotate(-90deg) translateX(50%);
    font-family: var(--font-mono);
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--color-text-muted);
}

.matrix-axis-x {
    position: absolute;
    bottom: -30px;
    left: 50%;
    transform: translateX(-50%);
    font-family: var(--font-mono);
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--color-text-muted);
}
```

### Priority Ranking Table
```css
.priority-table {
    width: 100%;
    border-collapse: collapse;
}

.priority-table th {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1px;
    text-align: left;
    padding: 16px;
    background: var(--color-primary);
    color: white;
    border: var(--border-width) solid var(--color-border);
}

.priority-table td {
    padding: 16px;
    border: var(--border-width) solid var(--color-border);
    font-size: 14px;
}

.priority-rank {
    font-family: var(--font-mono);
    font-size: 18px;
    font-weight: 700;
    width: 50px;
    text-align: center;
}

.priority-rank.top-3 {
    color: var(--color-primary);
}

.score-bar {
    height: 8px;
    background: var(--color-surface-variant, #e5e5e5);
    border-radius: 4px;
    overflow: hidden;
    margin-top: 8px;
}

.score-fill {
    height: 100%;
    background: var(--color-primary);
    border-radius: 4px;
}
```

### Kano Diagram
```css
.kano-chart {
    position: relative;
    width: 100%;
    height: 400px;
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
}

.kano-axis {
    position: absolute;
    background: var(--color-border);
}

.kano-axis-x {
    width: 100%;
    height: 2px;
    top: 50%;
    left: 0;
}

.kano-axis-y {
    width: 2px;
    height: 100%;
    top: 0;
    left: 50%;
}

.kano-curve {
    position: absolute;
    stroke: var(--color-primary);
    stroke-width: 3;
    fill: none;
}

.kano-label {
    position: absolute;
    font-family: var(--font-mono);
    font-size: 12px;
    font-weight: 600;
    padding: 4px 8px;
    border-radius: var(--radius-sm);
}

.kano-delighter { background: #D1FAE5; color: #065F46; }
.kano-performance { background: #DBEAFE; color: #1E40AF; }
.kano-basic { background: #FEE2E2; color: #991B1B; }
```

## Output Location

Save prioritization docs to: `./outputs/[project]-prioritization.html`
