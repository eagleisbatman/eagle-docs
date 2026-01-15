---
name: onboarding-docs-design
description: Create professional onboarding documentation as HTML. Includes new employee guides, developer setup docs, team handbooks, and getting started tutorials. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Outputs are desktop-optimized with one section per viewport. Use when user requests onboarding documentation, new hire guide, developer setup, team handbook, or getting started guide.
---

# Onboarding Documentation Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional onboarding documentation as self-contained HTML files. Each section occupies one viewport with scroll-based navigation. Optimized for desktop/laptop viewing (1024px+).

## Theme Support

Before generating, check for user preferences:

1. **Config file**: Look for `.eagle-docs.yaml` in project root
2. **Runtime prompt**: Ask user if no config exists

Available themes:
- **Brutalist** — Bold black-and-white, harsh shadows, no-nonsense
- **Material 3** — Rounded corners, elevation shadows, welcoming feel
- **Cupertino** — Apple-style, subtle gradients, premium look
- **Modern Minimal** — Clean lines, generous whitespace, contemporary

See `shared/DESIGN-SYSTEM.md` for complete theme specifications.

## Document Structure (Required Sections)

1. **Welcome** - Warm introduction, what to expect
2. **Before You Start** - Prerequisites, account setup
3. **Day 1 Checklist** - First day tasks and goals
4. **Week 1 Milestones** - First week objectives
5. **Development Environment** - Setup guides, tools
6. **Codebase Overview** - Architecture, key repositories
7. **Team & Communication** - Who's who, channels, meetings
8. **Processes & Workflows** - How we work, PR process, deployments
9. **Resources & Documentation** - Where to find things
10. **FAQ** - Common questions
11. **Getting Help** - Support channels, mentors

## Key Components

### Welcome Banner
```css
.welcome-banner {
    background: var(--color-primary);
    color: white;
    padding: 60px;
    text-align: center;
    margin-bottom: 48px;
}

.welcome-title {
    font-family: var(--font-heading);
    font-size: 42px;
    font-weight: 700;
    margin-bottom: 16px;
}

.welcome-subtitle {
    font-size: 18px;
    opacity: 0.9;
    max-width: 600px;
    margin: 0 auto;
}
```

### Progress Tracker
```css
.progress-tracker {
    display: flex;
    justify-content: space-between;
    margin: 48px 0;
    position: relative;
}

.progress-tracker::before {
    content: '';
    position: absolute;
    top: 20px;
    left: 40px;
    right: 40px;
    height: 3px;
    background: var(--color-border);
}

.progress-step {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    z-index: 1;
}

.step-circle {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background: var(--color-surface);
    border: 3px solid var(--color-border);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--font-mono);
    font-size: 14px;
    font-weight: 700;
    margin-bottom: 12px;
}

.step-circle.completed {
    background: var(--color-primary);
    border-color: var(--color-primary);
    color: white;
}

.step-circle.current {
    border-color: var(--color-primary);
    color: var(--color-primary);
}

.step-label {
    font-family: var(--font-mono);
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--color-text-muted);
}
```

### Checklist Card
```css
.checklist-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    margin-bottom: 24px;
    box-shadow: var(--shadow-md);
}

.checklist-header {
    background: var(--color-primary);
    color: white;
    padding: 20px 24px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.checklist-title {
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 700;
}

.checklist-progress {
    font-family: var(--font-mono);
    font-size: 14px;
    opacity: 0.9;
}

.checklist-items {
    padding: 0;
    margin: 0;
    list-style: none;
}

.checklist-item {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 20px 24px;
    border-bottom: 1px solid var(--color-border);
}

.checklist-item:last-child {
    border-bottom: none;
}

.checkbox {
    width: 24px;
    height: 24px;
    border: 2px solid var(--color-border);
    border-radius: var(--radius-sm);
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: center;
}

.checkbox.checked {
    background: var(--color-primary);
    border-color: var(--color-primary);
    color: white;
}

.item-content {
    flex: 1;
}

.item-title {
    font-size: 15px;
    font-weight: 500;
    margin-bottom: 4px;
}

.item-description {
    font-size: 14px;
    color: var(--color-text-muted);
}

.item-time {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--color-text-muted);
    white-space: nowrap;
}
```

### Team Member Card
```css
.team-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 24px;
}

.team-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    padding: 24px;
    border-radius: var(--radius-md);
}

.team-avatar {
    width: 64px;
    height: 64px;
    background: var(--color-primary);
    color: white;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--font-mono);
    font-size: 24px;
    font-weight: 700;
    margin-bottom: 16px;
}

.team-name {
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 600;
    margin-bottom: 4px;
}

.team-role {
    font-size: 14px;
    color: var(--color-text-muted);
    margin-bottom: 16px;
}

.team-contact {
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.contact-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 13px;
    color: var(--color-text-muted);
}

.contact-item a {
    color: var(--color-primary);
    text-decoration: none;
}
```

### Setup Step Card
```css
.setup-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    margin-bottom: 24px;
    box-shadow: var(--shadow-sm);
}

.setup-header {
    padding: 20px 24px;
    border-bottom: var(--border-width) solid var(--color-border);
    display: flex;
    align-items: center;
    gap: 16px;
}

.setup-number {
    width: 36px;
    height: 36px;
    background: var(--color-primary);
    color: white;
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--font-mono);
    font-size: 16px;
    font-weight: 700;
}

.setup-title {
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 600;
}

.setup-time {
    margin-left: auto;
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--color-text-muted);
}

.setup-body {
    padding: 24px;
}

.setup-description {
    font-size: 15px;
    margin-bottom: 20px;
}

.setup-code {
    background: #1a1a1a;
    color: #f5f5f5;
    padding: 16px 20px;
    border-radius: var(--radius-sm);
    font-family: var(--font-mono);
    font-size: 13px;
    overflow-x: auto;
    margin-bottom: 16px;
}

.setup-note {
    background: var(--color-surface-variant, #f5f5f5);
    padding: 12px 16px;
    border-radius: var(--radius-sm);
    font-size: 14px;
    display: flex;
    gap: 12px;
    align-items: flex-start;
}

.note-icon {
    color: var(--color-primary);
    flex-shrink: 0;
}
```

### Resource Link Card
```css
.resource-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 16px;
}

.resource-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    padding: 20px;
    border-radius: var(--radius-md);
    display: flex;
    align-items: center;
    gap: 16px;
    text-decoration: none;
    color: inherit;
    transition: box-shadow 0.2s ease;
}

.resource-card:hover {
    box-shadow: var(--shadow-md);
}

.resource-icon {
    width: 40px;
    height: 40px;
    background: var(--color-surface-variant, #f5f5f5);
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--color-primary);
}

.resource-info {
    flex: 1;
}

.resource-title {
    font-family: var(--font-heading);
    font-size: 15px;
    font-weight: 600;
    margin-bottom: 2px;
}

.resource-description {
    font-size: 13px;
    color: var(--color-text-muted);
}
```

## Section Content Guidelines

### Welcome
- Warm, friendly greeting
- What to expect from onboarding
- Timeline overview
- Who to contact for help

### Before You Start
- Account setup (email, Slack, GitHub, etc.)
- Hardware/equipment checklist
- Required software downloads
- Access requests to submit

### Day 1 Checklist
- Meeting your team
- Setting up workstation
- First code checkout
- Key introductions

### Week 1 Milestones
- Learning objectives
- First PR goal
- Documentation to read
- Meetings to attend

### Development Environment
- Step-by-step setup guides
- Required tools and versions
- IDE configuration
- Common setup issues

### Codebase Overview
- Repository structure
- Key services explained
- Architecture diagrams
- Coding standards

### Team & Communication
- Team member profiles
- Communication channels (Slack, email)
- Meeting schedule
- Escalation paths

### Processes & Workflows
- Git workflow
- PR review process
- Deployment procedures
- On-call expectations

### Resources & Documentation
- Link directory
- Internal wikis
- External docs
- Learning resources

### FAQ
- Common new hire questions
- Technical questions
- HR/admin questions

### Getting Help
- Mentor assignment
- Support channels
- Office hours
- Emergency contacts

## Output Location

Save onboarding docs to: `./outputs/[team-name]-onboarding.html`
