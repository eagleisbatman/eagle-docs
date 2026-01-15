---
name: business-canvas-design
description: Create professional business canvas documents as HTML. Includes Business Model Canvas, Lean Canvas, and Value Proposition Canvas with interactive layouts. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Use when user requests business model canvas, lean canvas, value proposition canvas, business model documentation, or startup canvas.
---

# Business Canvas Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional business canvas documents as self-contained HTML files. Supports Business Model Canvas, Lean Canvas, and Value Proposition Canvas with proper visual layouts. Optimized for desktop/laptop viewing (1024px+).

## Theme Support

Before generating, check for user preferences:

1. **Config file**: Look for `.eagle-docs.yaml` in project root
2. **Runtime prompt**: Ask user if no config exists

Available themes:
- **Brutalist** — Bold black-and-white, structured
- **Material 3** — Rounded corners, modern feel
- **Cupertino** — Apple-style, premium look
- **Modern Minimal** — Clean, whitespace-focused

See `shared/DESIGN-SYSTEM.md` for complete theme specifications.

## Supported Canvas Types

### 1. Business Model Canvas (Osterwalder)
Nine building blocks:
- Key Partners
- Key Activities
- Key Resources
- Value Propositions
- Customer Relationships
- Channels
- Customer Segments
- Cost Structure
- Revenue Streams

### 2. Lean Canvas (Ash Maurya)
Nine blocks adapted for startups:
- Problem
- Solution
- Key Metrics
- Unique Value Proposition
- Unfair Advantage
- Channels
- Customer Segments
- Cost Structure
- Revenue Streams

### 3. Value Proposition Canvas
Two sides:
- **Customer Profile**: Jobs, Pains, Gains
- **Value Map**: Products/Services, Pain Relievers, Gain Creators

## Document Structure

1. **Canvas Overview** - Which canvas, company/product name
2. **Full Canvas View** - Visual canvas layout
3. **Block Details** - Expanded explanation of each block
4. **Assumptions & Risks** - Key hypotheses to validate
5. **Next Steps** - Action items, experiments to run

## Key Components

### Business Model Canvas Layout
```css
.bmc-canvas {
    display: grid;
    grid-template-columns: 1fr 1fr 2fr 1fr 1fr;
    grid-template-rows: repeat(4, auto);
    gap: 4px;
    background: var(--color-border);
    border: var(--border-width) solid var(--color-border);
    margin: 32px 0;
}

.bmc-block {
    background: var(--color-surface);
    padding: 20px;
    min-height: 180px;
}

.bmc-block-header {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 16px;
}

.bmc-block-icon {
    width: 24px;
    height: 24px;
    color: var(--color-primary);
}

.bmc-block-title {
    font-family: var(--font-heading);
    font-size: 12px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.bmc-block-content {
    font-size: 13px;
    line-height: 1.7;
}

.bmc-block-content ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

.bmc-block-content li {
    padding: 6px 0;
    padding-left: 16px;
    position: relative;
}

.bmc-block-content li::before {
    content: '•';
    position: absolute;
    left: 0;
    color: var(--color-primary);
    font-weight: 700;
}

/* Grid positioning for BMC */
.bmc-partners { grid-column: 1; grid-row: 1 / 3; }
.bmc-activities { grid-column: 2; grid-row: 1; }
.bmc-resources { grid-column: 2; grid-row: 2; }
.bmc-value-prop { grid-column: 3; grid-row: 1 / 3; }
.bmc-relationships { grid-column: 4; grid-row: 1; }
.bmc-channels { grid-column: 4; grid-row: 2; }
.bmc-segments { grid-column: 5; grid-row: 1 / 3; }
.bmc-costs { grid-column: 1 / 4; grid-row: 3; }
.bmc-revenue { grid-column: 4 / 6; grid-row: 3; }
```

### Lean Canvas Layout
```css
.lean-canvas {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-template-rows: repeat(3, auto);
    gap: 4px;
    background: var(--color-border);
    border: var(--border-width) solid var(--color-border);
    margin: 32px 0;
}

.lean-block {
    background: var(--color-surface);
    padding: 20px;
    min-height: 160px;
}

/* Grid positioning for Lean Canvas */
.lean-problem { grid-column: 1; grid-row: 1 / 3; }
.lean-solution { grid-column: 2; grid-row: 1; }
.lean-metrics { grid-column: 2; grid-row: 2; }
.lean-uvp { grid-column: 3; grid-row: 1 / 3; }
.lean-advantage { grid-column: 4; grid-row: 1; }
.lean-channels { grid-column: 4; grid-row: 2; }
.lean-segments { grid-column: 5; grid-row: 1 / 3; }
.lean-costs { grid-column: 1 / 4; grid-row: 3; }
.lean-revenue { grid-column: 4 / 6; grid-row: 3; }

/* Highlight UVP block */
.lean-uvp {
    background: var(--color-primary);
    color: white;
}

.lean-uvp .bmc-block-title {
    color: rgba(255,255,255,0.8);
}
```

### Value Proposition Canvas Layout
```css
.vpc-canvas {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 40px;
    margin: 32px 0;
}

.vpc-side {
    border: var(--border-width) solid var(--color-border);
    border-radius: var(--radius-md);
    overflow: hidden;
}

.vpc-side-header {
    background: var(--color-primary);
    color: white;
    padding: 20px 24px;
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 700;
}

.vpc-customer .vpc-side-header {
    background: #1E40AF;
}

.vpc-value .vpc-side-header {
    background: #065F46;
}

.vpc-sections {
    padding: 24px;
}

.vpc-section {
    margin-bottom: 24px;
}

.vpc-section:last-child {
    margin-bottom: 0;
}

.vpc-section-title {
    font-family: var(--font-heading);
    font-size: 14px;
    font-weight: 700;
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
}

.vpc-section-title .icon {
    width: 18px;
    height: 18px;
}

.vpc-jobs .vpc-section-title { color: #1E40AF; }
.vpc-pains .vpc-section-title { color: #991B1B; }
.vpc-gains .vpc-section-title { color: #065F46; }

.vpc-items {
    background: var(--color-surface-variant, #f5f5f5);
    padding: 16px;
    border-radius: var(--radius-sm);
}

.vpc-item {
    padding: 8px 0;
    font-size: 14px;
    border-bottom: 1px solid var(--color-border);
}

.vpc-item:last-child {
    border-bottom: none;
}
```

### Canvas Block Detail Card
```css
.block-detail {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    margin-bottom: 24px;
    box-shadow: var(--shadow-sm);
}

.block-detail-header {
    padding: 20px 24px;
    border-bottom: var(--border-width) solid var(--color-border);
    display: flex;
    align-items: center;
    gap: 16px;
}

.block-detail-icon {
    width: 40px;
    height: 40px;
    background: var(--color-primary);
    color: white;
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    justify-content: center;
}

.block-detail-title {
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 700;
}

.block-detail-body {
    padding: 24px;
}

.block-detail-description {
    font-size: 15px;
    color: var(--color-text-muted);
    margin-bottom: 20px;
}

.block-detail-items {
    list-style: none;
    padding: 0;
    margin: 0;
}

.block-detail-items li {
    padding: 12px 16px;
    background: var(--color-surface-variant, #f5f5f5);
    margin-bottom: 8px;
    border-radius: var(--radius-sm);
    font-size: 14px;
}
```

### Assumption Card
```css
.assumption-card {
    border: var(--border-width) solid var(--color-border);
    margin-bottom: 16px;
    display: flex;
}

.assumption-risk {
    width: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--font-mono);
    font-size: 12px;
    font-weight: 700;
    writing-mode: vertical-lr;
    transform: rotate(180deg);
}

.risk-high { background: #FEE2E2; color: #991B1B; }
.risk-medium { background: #FEF3C7; color: #92400E; }
.risk-low { background: #D1FAE5; color: #065F46; }

.assumption-content {
    flex: 1;
    padding: 16px 20px;
}

.assumption-text {
    font-size: 15px;
    margin-bottom: 8px;
}

.assumption-validation {
    font-size: 13px;
    color: var(--color-text-muted);
}
```

## Section Guidelines

### Full Canvas View
- Single-page visual of entire canvas
- All blocks visible at once
- Print-friendly layout

### Block Details
- One section per block
- Expanded explanations
- Supporting evidence
- Related assumptions

### Assumptions & Risks
- Key hypotheses listed
- Risk level assigned
- Validation approach
- Experiment ideas

### Next Steps
- Prioritized action items
- Experiments to run
- Metrics to track
- Timeline suggestions

## Output Location

Save canvas docs to: `./outputs/[company]-business-canvas.html`
