---
name: strategic-analysis-design
description: Create professional strategic analysis documents as HTML. Includes PESTEL analysis, SWOT analysis, Porter's Five Forces, and Competitive Analysis frameworks. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Use when user requests PESTEL, SWOT, competitive analysis, market analysis, Porter's Five Forces, or strategic planning documentation.
---

# Strategic Analysis Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional strategic analysis documents as self-contained HTML files. Supports multiple strategic frameworks with visual layouts. Optimized for desktop/laptop viewing (1024px+).

## Theme Support

Before generating, check for user preferences:

1. **Config file**: Look for `.eagle-docs.yaml` in project root
2. **Runtime prompt**: Ask user if no config exists

Available themes:
- **Brutalist** — Bold black-and-white, analytical
- **Material 3** — Rounded corners, modern feel
- **Cupertino** — Apple-style, premium look
- **Modern Minimal** — Clean, whitespace-focused

See `shared/DESIGN-SYSTEM.md` for complete theme specifications.

## Supported Frameworks

### 1. PESTEL Analysis
Six macro-environmental factors:
- **P**olitical — Government policies, regulations, trade
- **E**conomic — Growth rates, inflation, exchange rates
- **S**ocial — Demographics, culture, lifestyle trends
- **T**echnological — Innovation, R&D, automation
- **E**nvironmental — Climate, sustainability, resources
- **L**egal — Laws, compliance, industry regulations

### 2. SWOT Analysis
Internal and external factors:
- **S**trengths — Internal advantages
- **W**eaknesses — Internal limitations
- **O**pportunities — External possibilities
- **T**hreats — External risks

### 3. Porter's Five Forces
Competitive intensity factors:
- Threat of New Entrants
- Bargaining Power of Suppliers
- Bargaining Power of Buyers
- Threat of Substitutes
- Industry Rivalry

### 4. Competitive Analysis
Competitor comparison:
- Market positioning
- Product comparison
- Pricing analysis
- Strengths/weaknesses
- Market share

## Document Structure

1. **Executive Summary** - Key findings, recommendations
2. **Framework Overview** - Methodology explanation
3. **Analysis** - Detailed framework application
4. **Insights** - Key takeaways
5. **Strategic Implications** - What it means
6. **Recommendations** - Action items
7. **Appendix** - Data sources, methodology

## Key Components

### PESTEL Grid
```css
.pestel-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, auto);
    gap: 24px;
    margin: 32px 0;
}

.pestel-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    border-radius: var(--radius-md);
    overflow: hidden;
    box-shadow: var(--shadow-sm);
}

.pestel-header {
    padding: 20px;
    display: flex;
    align-items: center;
    gap: 12px;
}

.pestel-icon {
    width: 40px;
    height: 40px;
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
}

.pestel-political .pestel-icon { background: #DC2626; }
.pestel-economic .pestel-icon { background: #2563EB; }
.pestel-social .pestel-icon { background: #7C3AED; }
.pestel-technological .pestel-icon { background: #0891B2; }
.pestel-environmental .pestel-icon { background: #16A34A; }
.pestel-legal .pestel-icon { background: #CA8A04; }

.pestel-title {
    font-family: var(--font-heading);
    font-size: 16px;
    font-weight: 700;
}

.pestel-letter {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--color-text-muted);
}

.pestel-body {
    padding: 0 20px 20px 20px;
}

.pestel-factors {
    list-style: none;
    padding: 0;
    margin: 0;
}

.pestel-factor {
    padding: 12px 0;
    border-bottom: 1px solid var(--color-border);
    font-size: 14px;
}

.pestel-factor:last-child {
    border-bottom: none;
}

.factor-impact {
    display: inline-block;
    font-family: var(--font-mono);
    font-size: 10px;
    padding: 2px 8px;
    border-radius: var(--radius-sm);
    margin-left: 8px;
}

.impact-high { background: #FEE2E2; color: #991B1B; }
.impact-medium { background: #FEF3C7; color: #92400E; }
.impact-low { background: #D1FAE5; color: #065F46; }
```

### SWOT Matrix
```css
.swot-matrix {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto auto;
    gap: 4px;
    background: var(--color-border);
    border: var(--border-width) solid var(--color-border);
    margin: 32px 0;
}

.swot-quadrant {
    background: var(--color-surface);
    padding: 24px;
    min-height: 250px;
}

.swot-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 20px;
}

.swot-icon {
    width: 36px;
    height: 36px;
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
}

.swot-strengths .swot-icon { background: #16A34A; }
.swot-weaknesses .swot-icon { background: #DC2626; }
.swot-opportunities .swot-icon { background: #2563EB; }
.swot-threats .swot-icon { background: #CA8A04; }

.swot-title {
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 700;
}

.swot-type {
    font-family: var(--font-mono);
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--color-text-muted);
}

.swot-items {
    list-style: none;
    padding: 0;
    margin: 0;
}

.swot-item {
    padding: 10px 0;
    font-size: 14px;
    display: flex;
    align-items: flex-start;
    gap: 10px;
}

.swot-item::before {
    content: '•';
    color: var(--color-primary);
    font-weight: 700;
}

/* Labels */
.swot-label {
    position: absolute;
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 2px;
    color: var(--color-text-muted);
}
```

### Porter's Five Forces Diagram
```css
.porter-diagram {
    position: relative;
    width: 100%;
    max-width: 700px;
    margin: 48px auto;
    padding: 100px;
}

.porter-center {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 200px;
    height: 200px;
    background: var(--color-primary);
    color: white;
    border-radius: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 20px;
    z-index: 2;
}

.porter-center-title {
    font-family: var(--font-heading);
    font-size: 14px;
    font-weight: 700;
    margin-bottom: 8px;
}

.porter-center-value {
    font-family: var(--font-mono);
    font-size: 24px;
    font-weight: 700;
}

.porter-force {
    position: absolute;
    width: 180px;
    padding: 20px;
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    border-radius: var(--radius-md);
    text-align: center;
    box-shadow: var(--shadow-md);
}

.porter-force-title {
    font-family: var(--font-heading);
    font-size: 13px;
    font-weight: 700;
    margin-bottom: 8px;
}

.porter-force-level {
    font-family: var(--font-mono);
    font-size: 11px;
    padding: 4px 12px;
    border-radius: var(--radius-sm);
    display: inline-block;
}

.level-high { background: #FEE2E2; color: #991B1B; }
.level-medium { background: #FEF3C7; color: #92400E; }
.level-low { background: #D1FAE5; color: #065F46; }

/* Force positions */
.porter-new-entrants { top: 0; left: 50%; transform: translateX(-50%); }
.porter-suppliers { top: 50%; left: 0; transform: translateY(-50%); }
.porter-buyers { top: 50%; right: 0; transform: translateY(-50%); }
.porter-substitutes { bottom: 0; left: 50%; transform: translateX(-50%); }

/* Connecting lines */
.porter-lines {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    z-index: 1;
}

.porter-line {
    stroke: var(--color-border);
    stroke-width: 2;
    stroke-dasharray: 6;
}
```

### Competitive Analysis Table
```css
.competitor-table {
    width: 100%;
    border-collapse: collapse;
    margin: 32px 0;
}

.competitor-table th {
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

.competitor-table td {
    padding: 16px;
    border: var(--border-width) solid var(--color-border);
    font-size: 14px;
    vertical-align: top;
}

.competitor-name {
    font-family: var(--font-heading);
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 12px;
}

.competitor-logo {
    width: 32px;
    height: 32px;
    background: var(--color-surface-variant, #f5f5f5);
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    justify-content: center;
}

.competitor-you {
    background: var(--color-primary);
    color: white;
}

.competitor-rating {
    display: flex;
    gap: 4px;
}

.rating-dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: var(--color-border);
}

.rating-dot.filled {
    background: var(--color-primary);
}

.market-share-bar {
    height: 24px;
    background: var(--color-surface-variant, #e5e5e5);
    border-radius: var(--radius-sm);
    overflow: hidden;
    position: relative;
}

.market-share-fill {
    height: 100%;
    background: var(--color-primary);
}

.market-share-label {
    position: absolute;
    right: 8px;
    top: 50%;
    transform: translateY(-50%);
    font-family: var(--font-mono);
    font-size: 11px;
    font-weight: 700;
}
```

## Output Location

Save strategic analysis docs to: `./outputs/[company]-strategic-analysis.html`
