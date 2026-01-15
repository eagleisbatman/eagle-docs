---
name: content-pipeline-design
description: Create professional content generation pipeline documentation as HTML with brutalist styling. Includes data sources, AI script generation, TTS synthesis, audio processing, quality assurance, and scheduling. Outputs are desktop-optimized with one section per viewport. Use when user requests content pipeline documentation, AI generation workflow, TTS pipeline, audio processing documentation, or content automation design.
---

# Content Pipeline Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional content generation pipeline documentation as HTML files with brutalist black-and-white aesthetics. Each section occupies one viewport with scroll-based navigation.

## Document Structure (Required Sections)

1. **Overview** - Purpose, capabilities, pipeline metrics
2. **Architecture** - High-level flow, component details, tech stack
3. **Data Sources** - Weather, markets, news APIs
4. **Script Generation** - LLM prompts, output format, validation
5. **Text-to-Speech Synthesis** - TTS providers, voice config, fallbacks
6. **Audio Processing** - Merging, normalization, encoding
7. **Quality Assurance** - Validation rules, scoring, review process
8. **Scheduling & Orchestration** - Cron jobs, task queues, triggers
9. **Cost Management** - Per-unit costs, budget tracking, optimization
10. **Monitoring & Alerts** - Metrics, dashboards, alert rules
11. **Failure Recovery** - Retry strategy, fallbacks, dead letter queue
12. **Configuration Reference** - Environment variables, settings

## Key Components

### Pipeline Flow Diagram (SVG)
```html
<svg viewBox="0 0 1000 200" class="pipeline-diagram">
    <defs>
        <marker id="arrow" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto">
            <path d="M0,0 L0,6 L9,3 z" fill="#1a1a1a"/>
        </marker>
    </defs>
    
    <!-- Stage boxes -->
    <g transform="translate(20, 70)">
        <rect width="120" height="60" fill="#1a1a1a" stroke="#1a1a1a" stroke-width="2"/>
        <text x="60" y="35" text-anchor="middle" fill="#fff" font-family="JetBrains Mono" font-size="12">TRIGGER</text>
    </g>
    
    <path d="M140,100 L180,100" stroke="#1a1a1a" stroke-width="2" marker-end="url(#arrow)"/>
    
    <g transform="translate(180, 70)">
        <rect width="120" height="60" fill="#fff" stroke="#1a1a1a" stroke-width="2"/>
        <text x="60" y="35" text-anchor="middle" font-family="JetBrains Mono" font-size="12">DATA</text>
    </g>
    
    <!-- Continue pattern for remaining stages -->
</svg>
```

### Stage Card
```css
.stage-card {
    background: var(--white);
    border: 2px solid var(--black);
    margin-bottom: 24px;
    box-shadow: 6px 6px 0 var(--black);
}

.stage-header {
    background: var(--black);
    color: var(--white);
    padding: 16px 24px;
    display: flex;
    align-items: center;
    gap: 16px;
}

.stage-number {
    font-family: 'JetBrains Mono', monospace;
    font-size: 24px;
    font-weight: 700;
    opacity: 0.5;
}

.stage-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 16px;
    font-weight: 700;
}

.stage-body {
    padding: 24px;
}
```

### Code/Config Block
```css
.config-block {
    background: #1a1a1a;
    color: #f5f5f5;
    padding: 24px;
    margin: 20px 0;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    line-height: 1.6;
    border: 3px solid var(--black);
    box-shadow: 6px 6px 0 var(--mid-gray);
    overflow-x: auto;
}
```

### Cost Table
```css
.cost-table th {
    background: var(--black);
    color: var(--white);
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    text-transform: uppercase;
}

.cost-table td {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
}

.cost-total {
    background: var(--black);
    color: var(--white);
    font-weight: 700;
}
```

### Provider Card Grid
```css
.provider-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}

.provider-card {
    border: 2px solid var(--black);
    background: var(--white);
}

.provider-header {
    background: var(--bg-gray);
    padding: 16px;
    border-bottom: 2px solid var(--black);
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.provider-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 700;
}

.provider-badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 4px 8px;
    border: 1px solid var(--black);
}

.provider-badge.primary {
    background: var(--black);
    color: var(--white);
}
```

## Template Usage

Standard layout with:
- Pipeline flow SVG diagrams
- Stage cards for each pipeline step
- Provider comparison grids
- Cost breakdown tables
- Configuration code blocks
- Monitoring metrics dashboards

## Output Location
Save content pipeline docs to: `/mnt/user-data/outputs/`
