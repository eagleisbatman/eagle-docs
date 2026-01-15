---
name: user-guide-design
description: Create professional user guides and help documentation as HTML. Includes getting started guides, feature documentation, how-to tutorials, FAQs, and troubleshooting sections. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Outputs are desktop-optimized with one section per viewport. Use when user requests user guide, help documentation, how-to guide, tutorial, or end-user documentation.
---

# User Guide Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional user guides and help documentation as self-contained HTML files. Each section occupies one viewport with scroll-based navigation. Optimized for desktop/laptop viewing (1024px+).

## Theme Support

Before generating, check for user preferences:

1. **Config file**: Look for `.eagle-docs.yaml` in project root
2. **Runtime prompt**: Ask user if no config exists

Available themes:
- **Brutalist** — Bold black-and-white, harsh shadows, technical look
- **Material 3** — Rounded corners, elevation shadows, friendly feel
- **Cupertino** — Apple-style, subtle gradients, premium look
- **Modern Minimal** — Clean lines, generous whitespace, contemporary

See `shared/DESIGN-SYSTEM.md` for complete theme specifications.

## Document Structure (Required Sections)

1. **Welcome** - Product overview, key benefits, who it's for
2. **Getting Started** - Quick setup, first steps, initial configuration
3. **Core Concepts** - Key terminology, mental model, how it works
4. **Features Overview** - Feature list with brief descriptions
5. **Feature Guides** - Detailed how-to for each major feature
6. **Common Tasks** - Step-by-step tutorials for typical workflows
7. **Tips & Best Practices** - Pro tips, optimization advice
8. **Troubleshooting** - Common issues and solutions
9. **FAQ** - Frequently asked questions
10. **Glossary** - Terms and definitions
11. **Getting Help** - Support channels, community resources

## Key Components

### Step-by-Step Guide
```css
.step-guide {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    margin-bottom: 32px;
    box-shadow: var(--shadow-md);
}

.step-guide-header {
    background: var(--color-primary);
    color: white;
    padding: 16px 24px;
    display: flex;
    align-items: center;
    gap: 16px;
}

.step-guide-title {
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 700;
}

.step-item {
    display: flex;
    gap: 20px;
    padding: 24px;
    border-bottom: 1px solid var(--color-border);
}

.step-item:last-child {
    border-bottom: none;
}

.step-number {
    width: 40px;
    height: 40px;
    background: var(--color-primary);
    color: white;
    border-radius: var(--radius-md);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--font-mono);
    font-size: 16px;
    font-weight: 700;
    flex-shrink: 0;
}

.step-content {
    flex: 1;
}

.step-title {
    font-family: var(--font-heading);
    font-size: 16px;
    font-weight: 600;
    margin-bottom: 8px;
}

.step-description {
    font-size: 15px;
    line-height: 1.7;
    color: var(--color-text);
}

.step-note {
    background: var(--color-surface-variant, #f5f5f5);
    padding: 12px 16px;
    margin-top: 12px;
    border-left: 3px solid var(--color-accent);
    font-size: 14px;
}
```

### Feature Card
```css
.feature-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    padding: 24px;
    margin-bottom: 20px;
    border-radius: var(--radius-md);
}

.feature-icon {
    width: 48px;
    height: 48px;
    background: var(--color-primary);
    color: white;
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 16px;
}

.feature-title {
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 600;
    margin-bottom: 8px;
}

.feature-description {
    font-size: 15px;
    color: var(--color-text-muted);
    margin-bottom: 16px;
}

.feature-link {
    font-family: var(--font-mono);
    font-size: 13px;
    color: var(--color-primary);
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 6px;
}
```

### Callout Boxes
```css
.callout {
    padding: 20px 24px;
    margin: 24px 0;
    border-radius: var(--radius-md);
    display: flex;
    gap: 16px;
}

.callout-icon {
    flex-shrink: 0;
}

.callout-content {
    flex: 1;
}

.callout-title {
    font-family: var(--font-heading);
    font-size: 14px;
    font-weight: 600;
    margin-bottom: 4px;
}

.callout-info {
    background: #EFF6FF;
    border: 1px solid #BFDBFE;
    color: #1E40AF;
}

.callout-tip {
    background: #ECFDF5;
    border: 1px solid #A7F3D0;
    color: #065F46;
}

.callout-warning {
    background: #FFFBEB;
    border: 1px solid #FCD34D;
    color: #92400E;
}

.callout-danger {
    background: #FEF2F2;
    border: 1px solid #FECACA;
    color: #991B1B;
}
```

### FAQ Accordion
```css
.faq-item {
    border: var(--border-width) solid var(--color-border);
    margin-bottom: 12px;
    border-radius: var(--radius-sm);
}

.faq-question {
    padding: 20px 24px;
    font-family: var(--font-heading);
    font-size: 16px;
    font-weight: 600;
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    background: var(--color-surface);
}

.faq-question:hover {
    background: var(--color-surface-variant, #f9f9f9);
}

.faq-answer {
    padding: 0 24px 20px 24px;
    font-size: 15px;
    line-height: 1.7;
    color: var(--color-text-muted);
}
```

### Troubleshooting Card
```css
.troubleshoot-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    margin-bottom: 24px;
}

.troubleshoot-problem {
    background: var(--color-surface-variant, #f5f5f5);
    padding: 16px 24px;
    border-bottom: var(--border-width) solid var(--color-border);
}

.troubleshoot-label {
    font-family: var(--font-mono);
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--color-text-muted);
    margin-bottom: 4px;
}

.troubleshoot-title {
    font-family: var(--font-heading);
    font-size: 16px;
    font-weight: 600;
}

.troubleshoot-solution {
    padding: 20px 24px;
}

.solution-step {
    display: flex;
    gap: 12px;
    margin-bottom: 12px;
}

.solution-number {
    font-family: var(--font-mono);
    font-size: 12px;
    font-weight: 700;
    color: var(--color-primary);
}
```

## Section Content Guidelines

### Welcome
- Warm, friendly introduction
- What the product does (1-2 sentences)
- Key benefits (3-5 bullet points)
- Who should use this guide

### Getting Started
- Prerequisites (if any)
- Installation/setup steps
- First-time configuration
- "Hello World" equivalent

### Core Concepts
- Key terminology defined
- Mental model explanation
- How components relate
- Visual diagrams if helpful

### Features Overview
- Grid of feature cards
- Brief description each
- Links to detailed guides

### Feature Guides
- One section per major feature
- Step-by-step instructions
- Screenshots/examples
- Tips and gotchas

### Common Tasks
- Task-oriented tutorials
- Real-world scenarios
- Copy-paste examples
- Expected outcomes

### Tips & Best Practices
- Power user tips
- Performance optimization
- Security best practices
- Common mistakes to avoid

### Troubleshooting
- Problem → Solution format
- Error messages explained
- Step-by-step fixes
- When to contact support

### FAQ
- Accordion-style Q&A
- Grouped by category
- Links to detailed docs

### Glossary
- Alphabetical term list
- Clear, concise definitions
- Cross-references

### Getting Help
- Support channels
- Community forums
- Documentation feedback
- Emergency contacts

## Output Location

Save user guide files to: `./outputs/[product-name]-user-guide.html`
