---
name: user-research-design
description: Create professional user research documents as HTML. Includes User Personas, Customer Journey Maps, Jobs to be Done (JTBD), and Empathy Maps. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Use when user requests user personas, journey map, JTBD, empathy map, user research documentation, or customer insights.
---

# User Research Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional user research documents as self-contained HTML files. Supports User Personas, Journey Maps, JTBD frameworks, and Empathy Maps with visual layouts. Optimized for desktop/laptop viewing (1024px+).

## Theme Support

Before generating, check for user preferences:

1. **Config file**: Look for `.eagle-docs.yaml` in project root
2. **Runtime prompt**: Ask user if no config exists

Available themes:
- **Brutalist** — Bold black-and-white, structured
- **Material 3** — Rounded corners, friendly feel
- **Cupertino** — Apple-style, premium look
- **Modern Minimal** — Clean, whitespace-focused

See `shared/DESIGN-SYSTEM.md` for complete theme specifications.

## Supported Frameworks

### 1. User Personas
Detailed user archetypes:
- Demographics
- Goals & Motivations
- Pain Points & Frustrations
- Behaviors & Habits
- Tech Savviness
- Quote / Bio

### 2. Customer Journey Map
End-to-end experience:
- Stages / Phases
- Actions
- Thoughts
- Emotions
- Touchpoints
- Pain Points
- Opportunities

### 3. Jobs to be Done (JTBD)
Outcome-focused framework:
- Job Statement
- Functional Jobs
- Emotional Jobs
- Social Jobs
- Related Jobs
- Hiring Criteria

### 4. Empathy Map
User understanding:
- Says
- Thinks
- Does
- Feels
- Pains
- Gains

## Document Structure

1. **Research Overview** - Methodology, participants
2. **Key Findings** - Summary insights
3. **Personas / Maps** - Visual frameworks
4. **Detailed Insights** - Deep dive per segment
5. **Recommendations** - Design implications
6. **Appendix** - Raw data, methodology

## Key Components

### Persona Card
```css
.persona-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    border-radius: var(--radius-md);
    overflow: hidden;
    box-shadow: var(--shadow-lg);
    max-width: 900px;
    margin: 32px auto;
}

.persona-header {
    background: var(--color-primary);
    color: white;
    padding: 32px;
    display: flex;
    gap: 24px;
    align-items: center;
}

.persona-avatar {
    width: 100px;
    height: 100px;
    background: rgba(255,255,255,0.2);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 40px;
    flex-shrink: 0;
}

.persona-intro {
    flex: 1;
}

.persona-name {
    font-family: var(--font-heading);
    font-size: 28px;
    font-weight: 700;
    margin-bottom: 4px;
}

.persona-role {
    font-size: 16px;
    opacity: 0.9;
    margin-bottom: 12px;
}

.persona-quote {
    font-style: italic;
    font-size: 15px;
    opacity: 0.85;
    padding-left: 16px;
    border-left: 3px solid rgba(255,255,255,0.5);
}

.persona-body {
    padding: 32px;
}

.persona-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 32px;
}

.persona-section {
    margin-bottom: 24px;
}

.persona-section-title {
    font-family: var(--font-heading);
    font-size: 14px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    color: var(--color-primary);
}

.persona-list {
    list-style: none;
    padding: 0;
    margin: 0;
}

.persona-list li {
    padding: 10px 0;
    border-bottom: 1px solid var(--color-border);
    font-size: 14px;
    display: flex;
    align-items: flex-start;
    gap: 10px;
}

.persona-list li:last-child {
    border-bottom: none;
}

.persona-list li::before {
    content: '';
    width: 6px;
    height: 6px;
    background: var(--color-primary);
    border-radius: 50%;
    margin-top: 7px;
    flex-shrink: 0;
}

.persona-demographics {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
}

.demo-item {
    background: var(--color-surface-variant, #f5f5f5);
    padding: 12px 16px;
    border-radius: var(--radius-sm);
}

.demo-label {
    font-family: var(--font-mono);
    font-size: 10px;
    text-transform: uppercase;
    color: var(--color-text-muted);
    margin-bottom: 4px;
}

.demo-value {
    font-size: 15px;
    font-weight: 600;
}
```

### Journey Map
```css
.journey-map {
    overflow-x: auto;
    margin: 32px 0;
}

.journey-container {
    display: grid;
    grid-template-columns: 150px repeat(var(--stages, 5), minmax(200px, 1fr));
    min-width: 1000px;
}

.journey-row-label {
    background: var(--color-surface-variant, #f5f5f5);
    padding: 20px;
    font-family: var(--font-heading);
    font-size: 13px;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 8px;
    border: 1px solid var(--color-border);
}

.journey-stage-header {
    background: var(--color-primary);
    color: white;
    padding: 20px;
    text-align: center;
    border: 1px solid var(--color-border);
}

.stage-number {
    font-family: var(--font-mono);
    font-size: 11px;
    opacity: 0.8;
    margin-bottom: 4px;
}

.stage-name {
    font-family: var(--font-heading);
    font-size: 15px;
    font-weight: 700;
}

.journey-cell {
    padding: 20px;
    border: 1px solid var(--color-border);
    background: var(--color-surface);
    font-size: 13px;
    line-height: 1.6;
}

.journey-cell ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

.journey-cell li {
    padding: 6px 0;
    padding-left: 16px;
    position: relative;
}

.journey-cell li::before {
    content: '•';
    position: absolute;
    left: 0;
    color: var(--color-primary);
}

/* Emotion row */
.journey-emotions {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
}

.emotion-indicator {
    font-size: 24px;
}

.emotion-positive { color: #16A34A; }
.emotion-neutral { color: #CA8A04; }
.emotion-negative { color: #DC2626; }

/* Pain points row */
.journey-pain {
    background: #FEF2F2;
}

/* Opportunities row */
.journey-opportunity {
    background: #F0FDF4;
}
```

### JTBD Card
```css
.jtbd-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    margin-bottom: 24px;
    box-shadow: var(--shadow-md);
}

.jtbd-header {
    background: var(--color-primary);
    color: white;
    padding: 24px;
}

.jtbd-statement {
    font-family: var(--font-heading);
    font-size: 20px;
    font-weight: 700;
    line-height: 1.4;
}

.jtbd-template {
    font-size: 14px;
    opacity: 0.85;
    margin-top: 12px;
    font-style: italic;
}

.jtbd-body {
    padding: 24px;
}

.jtbd-sections {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
}

.jtbd-section {
    padding: 20px;
    background: var(--color-surface-variant, #f5f5f5);
    border-radius: var(--radius-sm);
}

.jtbd-section-title {
    font-family: var(--font-heading);
    font-size: 12px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
}

.jtbd-functional .jtbd-section-title { color: #2563EB; }
.jtbd-emotional .jtbd-section-title { color: #DC2626; }
.jtbd-social .jtbd-section-title { color: #7C3AED; }

.jtbd-items {
    list-style: none;
    padding: 0;
    margin: 0;
}

.jtbd-item {
    padding: 10px 0;
    font-size: 14px;
    border-bottom: 1px solid var(--color-border);
}

.jtbd-item:last-child {
    border-bottom: none;
}

/* Hiring criteria */
.hiring-criteria {
    margin-top: 24px;
    padding: 20px;
    background: #F0FDF4;
    border-radius: var(--radius-sm);
    border-left: 4px solid #16A34A;
}

.hiring-title {
    font-family: var(--font-heading);
    font-size: 14px;
    font-weight: 700;
    color: #065F46;
    margin-bottom: 12px;
}
```

### Empathy Map
```css
.empathy-map {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: repeat(3, auto);
    gap: 4px;
    background: var(--color-border);
    border: var(--border-width) solid var(--color-border);
    margin: 32px 0;
    max-width: 900px;
}

.empathy-center {
    grid-column: 1 / 3;
    grid-row: 2;
    background: var(--color-primary);
    color: white;
    padding: 24px;
    text-align: center;
}

.empathy-avatar {
    width: 60px;
    height: 60px;
    background: rgba(255,255,255,0.2);
    border-radius: 50%;
    margin: 0 auto 12px auto;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 28px;
}

.empathy-name {
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 700;
}

.empathy-quadrant {
    background: var(--color-surface);
    padding: 24px;
    min-height: 180px;
}

.empathy-header {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 16px;
}

.empathy-icon {
    width: 28px;
    height: 28px;
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
}

.empathy-says .empathy-icon { background: #2563EB; }
.empathy-thinks .empathy-icon { background: #7C3AED; }
.empathy-does .empathy-icon { background: #16A34A; }
.empathy-feels .empathy-icon { background: #DC2626; }

.empathy-title {
    font-family: var(--font-heading);
    font-size: 14px;
    font-weight: 700;
    text-transform: uppercase;
}

.empathy-items {
    list-style: none;
    padding: 0;
    margin: 0;
}

.empathy-item {
    padding: 8px 0;
    font-size: 14px;
    display: flex;
    align-items: flex-start;
    gap: 8px;
}

.empathy-item::before {
    content: '"';
    color: var(--color-primary);
    font-size: 20px;
    line-height: 1;
}

/* Pains and Gains row */
.empathy-pains-gains {
    grid-column: 1 / 3;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4px;
}

.empathy-pains {
    background: #FEF2F2;
    padding: 24px;
}

.empathy-gains {
    background: #F0FDF4;
    padding: 24px;
}

.empathy-pains .empathy-icon { background: #DC2626; }
.empathy-gains .empathy-icon { background: #16A34A; }
```

## Output Location

Save user research docs to: `./outputs/[project]-user-research.html`
