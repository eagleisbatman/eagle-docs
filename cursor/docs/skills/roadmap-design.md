---
name: roadmap-design
description: Create professional product roadmap documents as HTML. Includes Timeline Roadmaps, Now/Next/Later format, Theme-based Roadmaps, and Release Planning views. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Use when user requests product roadmap, feature roadmap, release plan, now-next-later roadmap, or quarterly planning documentation.
---

# Roadmap Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional product roadmap documents as self-contained HTML files. Supports multiple roadmap formats with visual timelines. Optimized for desktop/laptop viewing (1024px+).

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

## Supported Roadmap Formats

### 1. Timeline Roadmap
Traditional chronological view:
- Quarter/Month columns
- Swimlanes by team/theme
- Milestone markers
- Dependencies shown

### 2. Now/Next/Later
Commitment-based format:
- **Now** — Currently building (committed)
- **Next** — Up next (planned)
- **Later** — Future consideration (exploratory)

### 3. Theme-Based Roadmap
Organized by strategic themes:
- Theme groupings
- Initiatives per theme
- Progress indicators
- Goal alignment

### 4. Release Roadmap
Version-focused view:
- Release milestones
- Features per release
- Target dates
- Dependencies

## Document Structure

1. **Roadmap Overview** - Vision, time horizon, format
2. **Strategic Context** - Goals, themes, success metrics
3. **Roadmap View** - Main visual roadmap
4. **Initiative Details** - Breakdown per item
5. **Dependencies** - Cross-team dependencies
6. **Risks & Assumptions** - Key uncertainties
7. **Change Log** - Roadmap revisions

## Key Components

### Timeline Roadmap
```css
.timeline-roadmap {
    overflow-x: auto;
    margin: 32px 0;
}

.timeline-container {
    min-width: 1200px;
}

.timeline-header {
    display: grid;
    grid-template-columns: 200px repeat(var(--quarters, 4), 1fr);
    background: var(--color-primary);
    color: white;
}

.timeline-header-label {
    padding: 16px 20px;
    font-family: var(--font-heading);
    font-size: 14px;
    font-weight: 700;
    border-right: 1px solid rgba(255,255,255,0.2);
}

.timeline-quarter {
    padding: 16px 20px;
    text-align: center;
    border-right: 1px solid rgba(255,255,255,0.2);
}

.quarter-name {
    font-family: var(--font-mono);
    font-size: 12px;
    opacity: 0.8;
}

.quarter-label {
    font-family: var(--font-heading);
    font-size: 16px;
    font-weight: 700;
}

.timeline-swimlane {
    display: grid;
    grid-template-columns: 200px repeat(var(--quarters, 4), 1fr);
    border-bottom: var(--border-width) solid var(--color-border);
}

.swimlane-label {
    padding: 20px;
    background: var(--color-surface-variant, #f5f5f5);
    font-family: var(--font-heading);
    font-size: 14px;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 10px;
    border-right: var(--border-width) solid var(--color-border);
}

.swimlane-icon {
    width: 24px;
    height: 24px;
    color: var(--color-primary);
}

.timeline-cell {
    padding: 12px;
    border-right: 1px solid var(--color-border);
    background: var(--color-surface);
    min-height: 100px;
    position: relative;
}

.timeline-item {
    background: var(--color-primary);
    color: white;
    padding: 10px 14px;
    border-radius: var(--radius-sm);
    font-size: 13px;
    font-weight: 500;
    margin-bottom: 8px;
    position: relative;
}

.timeline-item.spans-2 {
    position: absolute;
    width: calc(200% - 24px);
    z-index: 1;
}

.timeline-item.spans-3 {
    position: absolute;
    width: calc(300% - 24px);
    z-index: 1;
}

.item-status {
    display: inline-block;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    margin-right: 8px;
}

.status-done { background: #16A34A; }
.status-in-progress { background: #F59E0B; }
.status-planned { background: #6B7280; }

/* Milestone marker */
.milestone {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 20px;
    height: 20px;
    background: var(--color-primary);
    border: 3px solid white;
    border-radius: 50%;
    box-shadow: var(--shadow-sm);
    z-index: 2;
}
```

### Now/Next/Later
```css
.nnl-roadmap {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    margin: 32px 0;
}

.nnl-column {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    border-radius: var(--radius-md);
    overflow: hidden;
}

.nnl-header {
    padding: 24px;
    text-align: center;
}

.nnl-now .nnl-header { background: #16A34A; color: white; }
.nnl-next .nnl-header { background: #2563EB; color: white; }
.nnl-later .nnl-header { background: #6B7280; color: white; }

.nnl-title {
    font-family: var(--font-heading);
    font-size: 24px;
    font-weight: 700;
    margin-bottom: 4px;
}

.nnl-subtitle {
    font-size: 13px;
    opacity: 0.9;
}

.nnl-commitment {
    font-family: var(--font-mono);
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-top: 8px;
    padding: 4px 12px;
    background: rgba(255,255,255,0.2);
    border-radius: var(--radius-sm);
    display: inline-block;
}

.nnl-items {
    padding: 16px;
}

.nnl-item {
    background: var(--color-surface-variant, #f5f5f5);
    border-radius: var(--radius-sm);
    padding: 16px;
    margin-bottom: 12px;
}

.nnl-item:last-child {
    margin-bottom: 0;
}

.nnl-item-title {
    font-family: var(--font-heading);
    font-size: 15px;
    font-weight: 600;
    margin-bottom: 8px;
}

.nnl-item-description {
    font-size: 13px;
    color: var(--color-text-muted);
    margin-bottom: 12px;
}

.nnl-item-meta {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
}

.nnl-tag {
    font-family: var(--font-mono);
    font-size: 10px;
    padding: 4px 8px;
    background: var(--color-surface);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-sm);
}
```

### Theme-Based Roadmap
```css
.theme-roadmap {
    margin: 32px 0;
}

.theme-section {
    margin-bottom: 32px;
}

.theme-header {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 20px 24px;
    background: var(--color-primary);
    color: white;
    border-radius: var(--radius-md) var(--radius-md) 0 0;
}

.theme-icon {
    width: 40px;
    height: 40px;
    background: rgba(255,255,255,0.2);
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    justify-content: center;
}

.theme-title {
    font-family: var(--font-heading);
    font-size: 20px;
    font-weight: 700;
}

.theme-goal {
    font-size: 14px;
    opacity: 0.9;
    margin-left: auto;
}

.theme-initiatives {
    border: var(--border-width) solid var(--color-border);
    border-top: none;
    border-radius: 0 0 var(--radius-md) var(--radius-md);
}

.initiative-row {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr 120px;
    padding: 16px 24px;
    border-bottom: 1px solid var(--color-border);
    align-items: center;
}

.initiative-row:last-child {
    border-bottom: none;
}

.initiative-name {
    font-weight: 600;
    font-size: 15px;
}

.initiative-owner {
    font-size: 13px;
    color: var(--color-text-muted);
}

.initiative-timeline {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--color-text-muted);
}

.initiative-status {
    display: flex;
    align-items: center;
    gap: 8px;
}

.status-indicator {
    width: 10px;
    height: 10px;
    border-radius: 50%;
}

.status-on-track { background: #16A34A; }
.status-at-risk { background: #F59E0B; }
.status-blocked { background: #DC2626; }
.status-not-started { background: #6B7280; }

.status-label {
    font-family: var(--font-mono);
    font-size: 11px;
}
```

### Release Roadmap
```css
.release-roadmap {
    margin: 32px 0;
}

.release-card {
    background: var(--color-surface);
    border: var(--border-width) solid var(--color-border);
    border-radius: var(--radius-md);
    margin-bottom: 24px;
    overflow: hidden;
}

.release-header {
    padding: 24px;
    display: flex;
    align-items: center;
    gap: 20px;
    border-bottom: var(--border-width) solid var(--color-border);
}

.release-version {
    font-family: var(--font-mono);
    font-size: 32px;
    font-weight: 700;
    color: var(--color-primary);
}

.release-info {
    flex: 1;
}

.release-name {
    font-family: var(--font-heading);
    font-size: 20px;
    font-weight: 700;
    margin-bottom: 4px;
}

.release-date {
    font-family: var(--font-mono);
    font-size: 13px;
    color: var(--color-text-muted);
}

.release-status-badge {
    font-family: var(--font-mono);
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    padding: 8px 16px;
    border-radius: var(--radius-sm);
}

.badge-released { background: #D1FAE5; color: #065F46; }
.badge-in-progress { background: #FEF3C7; color: #92400E; }
.badge-planned { background: #F3F4F6; color: #6B7280; }

.release-features {
    padding: 24px;
}

.feature-category {
    margin-bottom: 20px;
}

.feature-category:last-child {
    margin-bottom: 0;
}

.category-title {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--color-text-muted);
    margin-bottom: 12px;
}

.feature-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 12px;
}

.feature-item {
    background: var(--color-surface-variant, #f5f5f5);
    padding: 14px 16px;
    border-radius: var(--radius-sm);
    font-size: 14px;
    display: flex;
    align-items: center;
    gap: 10px;
}

.feature-icon {
    width: 20px;
    height: 20px;
    color: var(--color-primary);
}
```

## Output Location

Save roadmap docs to: `./outputs/[product]-roadmap.html`
