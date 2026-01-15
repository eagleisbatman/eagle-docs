---
name: technical-spec-design
description: Create professional technical specification documents as HTML. Includes system design, architecture decisions, component specifications, data flow diagrams, and implementation details. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Outputs are desktop-optimized with one section per viewport. Use when user requests technical spec, engineering spec, system design doc, architecture document, or RFC.
---

# Technical Spec Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional technical specification documents as self-contained HTML files. Each section occupies one viewport with scroll-based navigation. Optimized for desktop/laptop viewing (1024px+).

## Theme Support

Before generating, check for user preferences:

1. **Config file**: Look for `.eagle-docs.yaml` in project root
2. **Runtime prompt**: Ask user if no config exists

Available themes:
- **Brutalist** — Bold black-and-white, harsh shadows, developer-focused
- **Material 3** — Rounded corners, elevation shadows, Google's design
- **Cupertino** — Apple-style, subtle gradients, refined look
- **Modern Minimal** — Clean lines, generous whitespace, contemporary

See `shared/DESIGN-SYSTEM.md` for complete theme specifications.

## Document Structure (Required Sections)

1. **Overview** - Problem statement, proposed solution, scope
2. **Background** - Context, existing systems, why now
3. **Goals & Non-Goals** - What we're solving, what we're not
4. **System Architecture** - High-level design, component diagram
5. **Detailed Design** - Component specifications, interfaces
6. **Data Model** - Schema changes, data flow
7. **API Design** - Endpoints, contracts, versioning
8. **Security Considerations** - Auth, data protection, threats
9. **Testing Strategy** - Unit, integration, e2e approach
10. **Rollout Plan** - Phases, feature flags, monitoring
11. **Alternatives Considered** - Other approaches evaluated
12. **Open Questions** - Unresolved decisions, future work

## Key Components

### Decision Record Card
```css
.decision-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    margin-bottom: 24px;
    box-shadow: var(--shadow-md);
}

.decision-header {
    background: var(--color-primary);
    color: var(--color-on-primary, white);
    padding: 16px 24px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.decision-title {
    font-family: var(--font-heading);
    font-size: 16px;
    font-weight: 700;
}

.decision-status {
    font-family: var(--font-mono);
    font-size: 11px;
    padding: 4px 12px;
    border: 1px solid currentColor;
    text-transform: uppercase;
}

.decision-body {
    padding: 24px;
}

.decision-section {
    margin-bottom: 20px;
}

.decision-label {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--color-text-muted);
    margin-bottom: 8px;
}
```

### Architecture Diagram Container
```css
.architecture-diagram {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    padding: 40px;
    margin: 32px 0;
    box-shadow: var(--shadow-lg);
    overflow-x: auto;
}

.diagram-title {
    font-family: var(--font-heading);
    font-size: 14px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 24px;
    color: var(--color-text-muted);
}
```

### Component Spec Table
```css
.spec-table {
    width: 100%;
    border-collapse: collapse;
    margin: 24px 0;
}

.spec-table th {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1px;
    text-align: left;
    padding: 14px 16px;
    background: var(--color-primary);
    color: white;
    border: var(--border-width) solid var(--color-border);
}

.spec-table td {
    padding: 14px 16px;
    border: var(--border-width) solid var(--color-border);
    font-size: 14px;
    vertical-align: top;
}

.spec-name {
    font-family: var(--font-mono);
    font-weight: 600;
}

.spec-type {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--color-text-muted);
}
```

### Sequence Diagram (SVG)
```html
<svg viewBox="0 0 800 400" class="sequence-diagram">
    <!-- Participant boxes -->
    <g class="participant" transform="translate(50, 20)">
        <rect width="100" height="40" fill="var(--color-primary)" stroke="var(--color-border)"/>
        <text x="50" y="25" text-anchor="middle" fill="white" font-family="var(--font-mono)" font-size="12">Client</text>
    </g>

    <!-- Lifelines -->
    <line x1="100" y1="60" x2="100" y2="380" stroke="var(--color-border)" stroke-dasharray="4"/>

    <!-- Messages -->
    <g class="message">
        <line x1="100" y1="100" x2="300" y2="100" stroke="var(--color-primary)" stroke-width="2" marker-end="url(#arrow)"/>
        <text x="200" y="90" text-anchor="middle" font-family="var(--font-mono)" font-size="11">request()</text>
    </g>
</svg>
```

### Status Badge
```css
.status-badge {
    font-family: var(--font-mono);
    font-size: 10px;
    font-weight: 700;
    text-transform: uppercase;
    padding: 4px 10px;
    border-radius: var(--radius-sm);
}

.status-draft { background: var(--color-surface); border: 1px solid var(--color-border); }
.status-review { background: #FEF3C7; color: #92400E; }
.status-approved { background: #D1FAE5; color: #065F46; }
.status-implemented { background: var(--color-primary); color: white; }
```

## Section Content Guidelines

### Overview
- Problem statement (1-2 paragraphs)
- Proposed solution summary
- Key benefits
- Scope boundaries

### Background
- Current system state
- Pain points driving this work
- Related projects/dependencies
- Historical context

### Goals & Non-Goals
- Explicit goals with success criteria
- Non-goals to set expectations
- Future considerations

### System Architecture
- High-level component diagram
- Data flow overview
- External dependencies
- Technology choices with rationale

### Detailed Design
- Component-by-component breakdown
- Interface definitions
- State management
- Error handling approach

### Data Model
- Schema changes (if any)
- Data migration strategy
- Storage requirements
- Data retention policies

### API Design
- Endpoint specifications
- Request/response formats
- Authentication requirements
- Rate limiting

### Security Considerations
- Threat model
- Authentication/authorization
- Data encryption
- Audit logging

### Testing Strategy
- Unit test coverage goals
- Integration test approach
- E2E test scenarios
- Performance benchmarks

### Rollout Plan
- Phased rollout strategy
- Feature flags
- Rollback procedures
- Monitoring requirements

### Alternatives Considered
- Other approaches evaluated
- Pros/cons comparison
- Why chosen approach wins

### Open Questions
- Unresolved decisions
- Dependencies on other teams
- Future enhancements

## Output Location

Save technical spec files to: `./outputs/[spec-name]-tech-spec.html`
