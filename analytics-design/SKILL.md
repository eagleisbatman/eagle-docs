---
name: analytics-design
description: Create professional analytics framework documentation as HTML with brutalist styling. Includes event taxonomy, KPIs, funnel analysis, cohort analysis, A/B testing framework, and dashboard specifications. Outputs are desktop-optimized with one section per viewport. Use when user requests analytics documentation, event tracking spec, KPI framework, metrics design, or data pipeline documentation.
---

# Analytics Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional analytics framework documentation as HTML files with brutalist black-and-white aesthetics. Each section occupies one viewport with scroll-based navigation.

## Document Structure (Required Sections)

1. **Overview** - Purpose, goals, analytics stack
2. **Analytics Architecture** - Event schema, data flow
3. **Event Taxonomy** - Event categories, naming conventions
4. **User Properties** - User attributes, segmentation
5. **Key Metrics & KPIs** - North star, health metrics
6. **Dashboards** - Dashboard specs, visualizations
7. **Funnel Analysis** - Key funnels, conversion tracking
8. **Cohort Analysis** - Retention curves, cohort definitions
9. **A/B Testing Framework** - Experiment design
10. **Data Pipeline** - ETL, warehousing
11. **Privacy & Compliance** - GDPR, data retention

## Key Components

### Event Card
```css
.event-card {
    background: var(--white);
    border: 2px solid var(--black);
    margin-bottom: 20px;
}
.event-header {
    background: var(--black);
    color: var(--white);
    padding: 14px 20px;
    display: flex;
    justify-content: space-between;
}
.event-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 15px;
    font-weight: 700;
}
```

### KPI Card
```css
.kpi-card {
    border: 2px solid var(--black);
    box-shadow: 6px 6px 0 var(--black);
}
.kpi-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 36px;
    font-weight: 700;
}
```

### Funnel Visualization
```css
.funnel-bar {
    height: 48px;
    background: var(--black);
    color: var(--white);
    font-family: 'JetBrains Mono', monospace;
}
```

## Template Structure

Use the standard sidebar + main content layout with:
- Event taxonomy tables
- KPI metric grids
- Funnel bar visualizations  
- Cohort heatmap tables
- Data flow diagrams

## Output Location
Save analytics files to: `/mnt/user-data/outputs/`
