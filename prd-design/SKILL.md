---
name: prd-design
description: Create professional Product Requirements Documents (PRDs) as beautiful HTML documents with brutalist styling. Outputs are desktop-optimized with one section per viewport, scroll-based navigation, and consistent structure. Use when user requests PRD, product spec, requirements document, or product documentation.
---

# PRD Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional Product Requirements Documents as HTML files with brutalist black-and-white aesthetics. Each section occupies one viewport with scroll-based navigation. Optimized for desktop/laptop viewing (1024px+).

## PRD Structure (Required Sections)

Every PRD must include these sections in order:

1. **Executive Summary** - One-paragraph overview, key dates, status
2. **Problem Statement** - User pain points, market opportunity
3. **Goals & Success Metrics** - OKRs, KPIs with targets
4. **User Personas** - 2-4 primary user types with details
5. **User Stories & Requirements** - Prioritized feature list (MoSCoW)
6. **Scope** - In scope, out of scope, future considerations
7. **Technical Architecture** - High-level system design
8. **Timeline & Milestones** - Phases, dates, deliverables
9. **Risks & Mitigations** - Risk register with severity
10. **Appendix** - References, glossary, changelog

## Technical Setup

### Required Imports
```html
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
```

### Color Palette
```css
:root {
    --black: #1a1a1a;
    --dark-gray: #333333;
    --mid-gray: #666666;
    --light-gray: #999999;
    --border-gray: #dddddd;
    --bg-gray: #f5f5f5;
    --white: #ffffff;
    /* Priority colors */
    --priority-must: #1a1a1a;
    --priority-should: #666666;
    --priority-could: #999999;
    --priority-wont: #cccccc;
}
```

## Layout Structure

### Page Layout
```css
body {
    font-family: 'IBM Plex Sans', sans-serif;
    font-size: 17px;
    line-height: 1.7;
    background: var(--bg-gray);
    color: var(--black);
    margin: 0;
}

.sidebar-nav {
    width: 300px;
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    background: var(--white);
    border-right: 3px solid var(--black);
    padding: 32px;
    overflow-y: auto;
    z-index: 100;
}

.main-content {
    margin-left: 300px;
}
```

### Section Layout (One Per Viewport)
```css
.prd-section {
    min-height: 100vh;
    padding: 80px;
    border-bottom: 3px solid var(--black);
    max-width: 1000px;
    margin: 0 auto;
}

.prd-section:nth-child(even) {
    background: var(--white);
}

.section-number {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 600;
    color: var(--mid-gray);
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 8px;
}

.section-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 32px;
    font-weight: 700;
    margin-bottom: 40px;
    padding-bottom: 16px;
    border-bottom: 4px solid var(--black);
}
```

## Component Styles

### Info Cards
```css
.info-card {
    background: var(--white);
    border: 2px solid var(--black);
    padding: 28px;
    margin-bottom: 24px;
    box-shadow: 8px 8px 0 var(--black);
}

.info-card-header {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 16px;
    padding-bottom: 12px;
    border-bottom: 2px solid var(--black);
    display: flex;
    align-items: center;
    gap: 12px;
}
```

### Metadata Grid
```css
.metadata-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 24px;
    margin-bottom: 40px;
}

.metadata-item {
    border: 2px solid var(--black);
    padding: 20px;
}

.metadata-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--mid-gray);
    margin-bottom: 8px;
}

.metadata-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 18px;
    font-weight: 600;
}
```

### Tables
```css
.prd-table {
    width: 100%;
    border-collapse: collapse;
    margin: 24px 0;
    font-size: 15px;
}

.prd-table th {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 1px;
    text-align: left;
    padding: 16px;
    background: var(--black);
    color: var(--white);
    border: 2px solid var(--black);
}

.prd-table td {
    padding: 16px;
    border: 2px solid var(--black);
    vertical-align: top;
}

.prd-table tr:nth-child(even) {
    background: var(--bg-gray);
}
```

### Priority Badges
```css
.priority-badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    padding: 6px 12px;
    border: 2px solid;
    display: inline-block;
}

.priority-must {
    background: var(--black);
    color: var(--white);
    border-color: var(--black);
}

.priority-should {
    background: var(--white);
    color: var(--black);
    border-color: var(--black);
}

.priority-could {
    background: var(--bg-gray);
    color: var(--mid-gray);
    border-color: var(--mid-gray);
}
```

### User Persona Cards
```css
.persona-card {
    background: var(--white);
    border: 3px solid var(--black);
    padding: 32px;
    margin-bottom: 32px;
    box-shadow: 10px 10px 0 var(--black);
}

.persona-header {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-bottom: 24px;
    padding-bottom: 20px;
    border-bottom: 2px solid var(--black);
}

.persona-avatar {
    width: 80px;
    height: 80px;
    background: var(--black);
    color: var(--white);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 28px;
    font-weight: 700;
}

.persona-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 22px;
    font-weight: 700;
}

.persona-role {
    font-size: 15px;
    color: var(--mid-gray);
    margin-top: 4px;
}

.persona-details {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
}

.persona-section-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 12px;
    color: var(--mid-gray);
}
```

### Timeline
```css
.timeline {
    position: relative;
    padding-left: 40px;
}

.timeline::before {
    content: '';
    position: absolute;
    left: 12px;
    top: 0;
    bottom: 0;
    width: 3px;
    background: var(--black);
}

.timeline-item {
    position: relative;
    margin-bottom: 40px;
    padding: 24px;
    background: var(--white);
    border: 2px solid var(--black);
}

.timeline-item::before {
    content: '';
    position: absolute;
    left: -34px;
    top: 28px;
    width: 16px;
    height: 16px;
    background: var(--black);
    border: 3px solid var(--white);
    box-shadow: 0 0 0 3px var(--black);
}

.timeline-date {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    font-weight: 600;
    color: var(--mid-gray);
    margin-bottom: 8px;
}

.timeline-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 18px;
    font-weight: 700;
    margin-bottom: 12px;
}
```

### Risk Matrix
```css
.risk-item {
    border: 2px solid var(--black);
    padding: 20px;
    margin-bottom: 16px;
    display: grid;
    grid-template-columns: auto 1fr auto;
    gap: 20px;
    align-items: center;
}

.risk-severity {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    padding: 8px 16px;
    border: 2px solid var(--black);
}

.risk-high { background: var(--black); color: var(--white); }
.risk-medium { background: var(--bg-gray); }
.risk-low { background: var(--white); color: var(--mid-gray); }
```

## Complete Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Product Name] - PRD</title>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        :root {
            --black: #1a1a1a;
            --dark-gray: #333;
            --mid-gray: #666;
            --light-gray: #999;
            --border-gray: #ddd;
            --bg-gray: #f5f5f5;
            --white: #fff;
        }
        html { scroll-behavior: smooth; }
        body {
            font-family: 'IBM Plex Sans', sans-serif;
            font-size: 17px;
            line-height: 1.7;
            background: var(--bg-gray);
            color: var(--black);
        }
        
        /* Sidebar */
        .sidebar-nav {
            width: 300px;
            position: fixed;
            top: 0; left: 0;
            height: 100vh;
            background: var(--white);
            border-right: 3px solid var(--black);
            padding: 32px;
            overflow-y: auto;
            z-index: 100;
        }
        .doc-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 4px;
        }
        .doc-type {
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: var(--mid-gray);
            margin-bottom: 24px;
            padding-bottom: 20px;
            border-bottom: 2px solid var(--black);
        }
        .nav-list { list-style: none; }
        .nav-link {
            display: block;
            padding: 12px 16px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            color: var(--black);
            text-decoration: none;
            border: 2px solid transparent;
            margin-bottom: 4px;
        }
        .nav-link:hover { background: var(--bg-gray); border-color: var(--border-gray); }
        .nav-link.active { background: var(--black); color: var(--white); }
        .nav-number { display: inline-block; width: 32px; font-weight: 600; }
        
        /* Main Content */
        .main-content { margin-left: 300px; }
        
        /* Sections */
        .prd-section {
            min-height: 100vh;
            padding: 80px;
            border-bottom: 3px solid var(--black);
        }
        .prd-section:nth-child(even) { background: var(--white); }
        .section-inner { max-width: 900px; margin: 0 auto; }
        .section-number {
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            font-weight: 600;
            color: var(--mid-gray);
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 8px;
        }
        .section-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 32px;
            font-weight: 700;
            margin-bottom: 40px;
            padding-bottom: 16px;
            border-bottom: 4px solid var(--black);
        }
        
        /* Components */
        .metadata-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }
        .metadata-item { border: 2px solid var(--black); padding: 20px; background: var(--white); }
        .metadata-label {
            font-family: 'JetBrains Mono', monospace;
            font-size: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--mid-gray);
            margin-bottom: 8px;
        }
        .metadata-value {
            font-family: 'JetBrains Mono', monospace;
            font-size: 16px;
            font-weight: 600;
        }
        
        .content-block {
            background: var(--white);
            border: 2px solid var(--black);
            padding: 28px;
            margin-bottom: 24px;
            box-shadow: 6px 6px 0 var(--black);
        }
        .content-block-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 16px;
            padding-bottom: 12px;
            border-bottom: 2px solid var(--black);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .prd-table { width: 100%; border-collapse: collapse; margin: 24px 0; }
        .prd-table th {
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-align: left;
            padding: 14px 16px;
            background: var(--black);
            color: var(--white);
            border: 2px solid var(--black);
        }
        .prd-table td {
            padding: 14px 16px;
            border: 2px solid var(--black);
            font-size: 15px;
        }
        .prd-table tr:nth-child(even) { background: var(--bg-gray); }
        
        .priority-badge {
            font-family: 'JetBrains Mono', monospace;
            font-size: 10px;
            font-weight: 700;
            text-transform: uppercase;
            padding: 4px 10px;
            border: 2px solid var(--black);
        }
        .priority-must { background: var(--black); color: var(--white); }
        .priority-should { background: var(--white); }
        .priority-could { background: var(--bg-gray); color: var(--mid-gray); border-color: var(--mid-gray); }
        
        .persona-card {
            background: var(--white);
            border: 3px solid var(--black);
            padding: 28px;
            margin-bottom: 28px;
            box-shadow: 8px 8px 0 var(--black);
        }
        .persona-header {
            display: flex;
            align-items: center;
            gap: 20px;
            margin-bottom: 20px;
            padding-bottom: 16px;
            border-bottom: 2px solid var(--black);
        }
        .persona-avatar {
            width: 64px; height: 64px;
            background: var(--black);
            color: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .persona-name {
            font-family: 'JetBrains Mono', monospace;
            font-size: 20px;
            font-weight: 700;
        }
        .persona-role { font-size: 14px; color: var(--mid-gray); margin-top: 4px; }
        
        .timeline { position: relative; padding-left: 40px; }
        .timeline::before {
            content: '';
            position: absolute;
            left: 10px; top: 0; bottom: 0;
            width: 3px;
            background: var(--black);
        }
        .timeline-item {
            position: relative;
            margin-bottom: 32px;
            padding: 20px;
            background: var(--white);
            border: 2px solid var(--black);
        }
        .timeline-item::before {
            content: '';
            position: absolute;
            left: -36px; top: 24px;
            width: 14px; height: 14px;
            background: var(--black);
            border: 3px solid var(--white);
            box-shadow: 0 0 0 3px var(--black);
        }
        .timeline-date {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            color: var(--mid-gray);
            margin-bottom: 6px;
        }
        .timeline-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 16px;
            font-weight: 700;
        }
        
        .icon { width: 20px; height: 20px; stroke-width: 2; }
        .icon-sm { width: 16px; height: 16px; }
        
        ul, ol { padding-left: 24px; margin: 16px 0; }
        li { margin-bottom: 10px; }
    </style>
</head>
<body>
    <!-- Sidebar Navigation -->
    <nav class="sidebar-nav">
        <div class="doc-title">[Product Name]</div>
        <div class="doc-type">Product Requirements Document</div>
        <ul class="nav-list">
            <li><a href="#executive-summary" class="nav-link"><span class="nav-number">01</span> Executive Summary</a></li>
            <li><a href="#problem" class="nav-link"><span class="nav-number">02</span> Problem Statement</a></li>
            <li><a href="#goals" class="nav-link"><span class="nav-number">03</span> Goals & Metrics</a></li>
            <li><a href="#personas" class="nav-link"><span class="nav-number">04</span> User Personas</a></li>
            <li><a href="#requirements" class="nav-link"><span class="nav-number">05</span> Requirements</a></li>
            <li><a href="#scope" class="nav-link"><span class="nav-number">06</span> Scope</a></li>
            <li><a href="#architecture" class="nav-link"><span class="nav-number">07</span> Architecture</a></li>
            <li><a href="#timeline" class="nav-link"><span class="nav-number">08</span> Timeline</a></li>
            <li><a href="#risks" class="nav-link"><span class="nav-number">09</span> Risks</a></li>
            <li><a href="#appendix" class="nav-link"><span class="nav-number">10</span> Appendix</a></li>
        </ul>
    </nav>

    <main class="main-content">
        <!-- Section 1: Executive Summary -->
        <section id="executive-summary" class="prd-section">
            <div class="section-inner">
                <div class="section-number">Section 01</div>
                <h1 class="section-title">Executive Summary</h1>
                
                <div class="metadata-grid">
                    <div class="metadata-item">
                        <div class="metadata-label">Version</div>
                        <div class="metadata-value">1.0</div>
                    </div>
                    <div class="metadata-item">
                        <div class="metadata-label">Status</div>
                        <div class="metadata-value">Draft</div>
                    </div>
                    <div class="metadata-item">
                        <div class="metadata-label">Author</div>
                        <div class="metadata-value">[Name]</div>
                    </div>
                    <div class="metadata-item">
                        <div class="metadata-label">Last Updated</div>
                        <div class="metadata-value">[Date]</div>
                    </div>
                </div>
                
                <div class="content-block">
                    <div class="content-block-title">
                        <i data-lucide="file-text" class="icon-sm"></i>
                        Overview
                    </div>
                    <p>[One paragraph summary of the product, its purpose, and key value proposition]</p>
                </div>
            </div>
        </section>

        <!-- Add remaining sections following same pattern -->
    </main>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            lucide.createIcons();
            
            // Active nav highlighting
            const sections = document.querySelectorAll('.prd-section');
            const navLinks = document.querySelectorAll('.nav-link');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => link.classList.remove('active'));
                        const activeLink = document.querySelector(`a[href="#${entry.target.id}"]`);
                        if (activeLink) activeLink.classList.add('active');
                    }
                });
            }, { threshold: 0.3 });
            
            sections.forEach(section => observer.observe(section));
        });
    </script>
</body>
</html>
```

## Section Content Guidelines

### Executive Summary
- Version, status, author, date metadata
- One-paragraph product overview
- Key stakeholders
- Target launch date

### Problem Statement  
- User pain points (bulleted)
- Market opportunity
- Current alternatives
- Why now?

### Goals & Success Metrics
- Primary OKRs (3-5)
- KPI table with baseline, target, stretch
- Success criteria for launch

### User Personas
- 2-4 persona cards
- Each includes: demographics, goals, pain points, tech comfort

### Requirements
- MoSCoW prioritized table
- User stories format: "As a [user], I want [feature], so that [benefit]"
- Priority badges: MUST, SHOULD, COULD

### Scope
- In scope (bulleted)
- Out of scope (bulleted)
- Future considerations

### Architecture
- High-level system diagram (can embed SVG)
- Technology stack table
- Integration points

### Timeline
- Timeline visualization
- Phase-based milestones
- Dependencies noted

### Risks
- Risk table: Risk, Probability, Impact, Mitigation
- Severity badges: HIGH, MEDIUM, LOW

### Appendix
- Glossary
- References
- Changelog table

## Output Location
Save PRD files to: `/mnt/user-data/outputs/`
