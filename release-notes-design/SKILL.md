---
name: release-notes-design
description: Create professional release notes and changelogs as HTML. Includes version history, feature announcements, bug fixes, breaking changes, and migration guides. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Outputs are desktop-optimized with one section per viewport. Use when user requests release notes, changelog, version history, what's new, or update documentation.
---

# Release Notes Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional release notes and changelogs as self-contained HTML files. Each version section is clearly delineated with scroll-based navigation. Optimized for desktop/laptop viewing (1024px+).

## Theme Support

Before generating, check for user preferences:

1. **Config file**: Look for `.eagle-docs.yaml` in project root
2. **Runtime prompt**: Ask user if no config exists

Available themes:
- **Brutalist** — Bold black-and-white, harsh shadows, technical look
- **Material 3** — Rounded corners, elevation shadows, modern feel
- **Cupertino** — Apple-style, subtle gradients, refined look
- **Modern Minimal** — Clean lines, generous whitespace, contemporary

See `shared/DESIGN-SYSTEM.md` for complete theme specifications.

## Document Structure (Required Sections)

1. **Header** - Product name, current version, last updated
2. **Latest Release** - Featured release with full details
3. **Version History** - Chronological list of all releases
4. **Upgrade Guide** - Migration instructions for breaking changes
5. **Deprecation Notices** - Features being removed
6. **Known Issues** - Current bugs and workarounds
7. **Roadmap Preview** - What's coming next

## Key Components

### Version Header
```css
.version-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 32px;
    padding-bottom: 24px;
    border-bottom: 3px solid var(--color-border);
}

.version-number {
    font-family: var(--font-mono);
    font-size: 48px;
    font-weight: 700;
    color: var(--color-primary);
    line-height: 1;
}

.version-meta {
    text-align: right;
}

.version-date {
    font-family: var(--font-mono);
    font-size: 14px;
    color: var(--color-text-muted);
    margin-bottom: 8px;
}

.version-tag {
    font-family: var(--font-mono);
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    padding: 6px 12px;
    border-radius: var(--radius-sm);
}

.tag-latest {
    background: var(--color-primary);
    color: white;
}

.tag-beta {
    background: #FEF3C7;
    color: #92400E;
}

.tag-lts {
    background: #D1FAE5;
    color: #065F46;
}
```

### Change Category
```css
.change-category {
    margin-bottom: 32px;
}

.category-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 16px;
}

.category-icon {
    width: 32px;
    height: 32px;
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    justify-content: center;
}

.category-new {
    background: #D1FAE5;
    color: #065F46;
}

.category-improved {
    background: #DBEAFE;
    color: #1E40AF;
}

.category-fixed {
    background: #FEE2E2;
    color: #991B1B;
}

.category-breaking {
    background: #FEF3C7;
    color: #92400E;
}

.category-deprecated {
    background: #F3F4F6;
    color: #6B7280;
}

.category-title {
    font-family: var(--font-heading);
    font-size: 18px;
    font-weight: 600;
}

.category-count {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--color-text-muted);
}
```

### Change Item
```css
.change-list {
    list-style: none;
    padding: 0;
}

.change-item {
    display: flex;
    gap: 16px;
    padding: 16px 0;
    border-bottom: 1px solid var(--color-border);
}

.change-item:last-child {
    border-bottom: none;
}

.change-bullet {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--color-primary);
    margin-top: 8px;
    flex-shrink: 0;
}

.change-content {
    flex: 1;
}

.change-title {
    font-size: 15px;
    font-weight: 500;
    margin-bottom: 4px;
}

.change-description {
    font-size: 14px;
    color: var(--color-text-muted);
    line-height: 1.6;
}

.change-tags {
    display: flex;
    gap: 8px;
    margin-top: 8px;
}

.change-tag {
    font-family: var(--font-mono);
    font-size: 10px;
    padding: 2px 8px;
    background: var(--color-surface-variant, #f5f5f5);
    border-radius: var(--radius-sm);
    color: var(--color-text-muted);
}

.change-pr {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--color-primary);
    text-decoration: none;
}
```

### Breaking Change Alert
```css
.breaking-change {
    background: #FEF3C7;
    border: 2px solid #F59E0B;
    padding: 24px;
    margin: 24px 0;
    border-radius: var(--radius-md);
}

.breaking-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 16px;
}

.breaking-icon {
    color: #D97706;
}

.breaking-title {
    font-family: var(--font-heading);
    font-size: 16px;
    font-weight: 700;
    color: #92400E;
}

.breaking-description {
    font-size: 14px;
    color: #92400E;
    margin-bottom: 16px;
}

.breaking-migration {
    background: white;
    padding: 16px;
    border-radius: var(--radius-sm);
}

.migration-label {
    font-family: var(--font-mono);
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: #92400E;
    margin-bottom: 8px;
}

.migration-code {
    font-family: var(--font-mono);
    font-size: 13px;
    background: #1a1a1a;
    color: #f5f5f5;
    padding: 12px;
    border-radius: var(--radius-sm);
    overflow-x: auto;
}
```

### Version Timeline
```css
.version-timeline {
    position: relative;
    padding-left: 32px;
}

.version-timeline::before {
    content: '';
    position: absolute;
    left: 8px;
    top: 0;
    bottom: 0;
    width: 2px;
    background: var(--color-border);
}

.timeline-item {
    position: relative;
    padding-bottom: 32px;
}

.timeline-item::before {
    content: '';
    position: absolute;
    left: -28px;
    top: 4px;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: var(--color-primary);
    border: 3px solid var(--color-surface);
}

.timeline-item.current::before {
    width: 16px;
    height: 16px;
    left: -30px;
    top: 2px;
}

.timeline-version {
    font-family: var(--font-mono);
    font-size: 18px;
    font-weight: 700;
    margin-bottom: 4px;
}

.timeline-date {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--color-text-muted);
    margin-bottom: 12px;
}

.timeline-summary {
    font-size: 14px;
    color: var(--color-text-muted);
}
```

## Section Content Guidelines

### Header
- Product name and logo
- Current stable version
- Last updated date
- Link to full changelog

### Latest Release
- Version number prominently displayed
- Release date
- Release highlights (3-5 key changes)
- Full categorized changelog
- Download/upgrade links

### Version History
- Chronological list (newest first)
- Collapsible sections for older versions
- Quick summary for each version
- Links to detailed notes

### Change Categories
Use these standard categories:
- **New** (green) — New features and capabilities
- **Improved** (blue) — Enhancements to existing features
- **Fixed** (red) — Bug fixes
- **Breaking** (orange) — Breaking changes requiring migration
- **Deprecated** (gray) — Features being phased out
- **Security** (purple) — Security patches

### Upgrade Guide
- Step-by-step migration instructions
- Before/after code examples
- Common migration issues
- Rollback procedures

### Deprecation Notices
- What's being deprecated
- When it will be removed
- Migration path
- Recommended alternatives

### Known Issues
- Current bugs with workarounds
- Expected fix timeline
- Severity indicators

### Roadmap Preview
- What's coming in next release
- Long-term planned features
- Community requested features

## Output Location

Save release notes files to: `./outputs/[product-name]-release-notes.html`
