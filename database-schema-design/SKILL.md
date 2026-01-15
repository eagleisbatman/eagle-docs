---
name: database-schema-design
description: Create professional database schema documentation as HTML. Includes ERD diagrams, table definitions, indexes, relationships, and migration strategies. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Outputs are desktop-optimized with one section per viewport. Use when user requests database design, schema documentation, ERD, data model, or table definitions.
---

# Database Schema Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional database schema documentation as self-contained HTML files. Each section occupies one viewport with scroll-based navigation. Optimized for desktop/laptop viewing (1024px+).

## Theme Support

Before generating, check for user preferences:

1. **Config file**: Look for `.eagle-docs.yaml` in project root
2. **Runtime prompt**: Ask user if no config exists

Available themes:
- **Brutalist** — Bold black-and-white, harsh shadows, technical aesthetic
- **Material 3** — Rounded corners, elevation shadows, Google's design
- **Cupertino** — Apple-style, subtle gradients, refined look
- **Modern Minimal** — Clean lines, generous whitespace, contemporary

See `shared/DESIGN-SYSTEM.md` for complete theme specifications.

## Schema Document Structure (Required Sections)

1. **Overview** - Database platform, schema summary, table count
2. **Design Principles** - Naming conventions, standard columns, policies
3. **Entity Relationship Diagram** - Visual ERD (SVG-based)
4. **Schema Definitions** - Complete table definitions with SQL
5. **Indexes & Performance** - Index strategy, query patterns
6. **Data Types & Enums** - Custom types, utility functions
7. **Partitioning Strategy** - Table partitioning, retention
8. **Migration Strategy** - Tooling, migration examples
9. **Seed Data** - Reference data scripts
10. **Backup & Recovery** - Backup strategy, DR procedures

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
    /* Data type colors */
    --type-pk: #1a1a1a;      /* Primary key */
    --type-fk: #666666;      /* Foreign key */
    --type-nullable: #999999; /* Nullable */
}
```

## Layout Structure

```css
body {
    font-family: 'IBM Plex Sans', sans-serif;
    font-size: 16px;
    line-height: 1.7;
    background: var(--bg-gray);
    color: var(--black);
}

.sidebar-nav {
    width: 300px;
    position: fixed;
    top: 0; left: 0;
    height: 100vh;
    background: var(--white);
    border-right: 3px solid var(--black);
    padding: 32px;
    overflow-y: auto;
}

.main-content { margin-left: 300px; }

.schema-section {
    min-height: 100vh;
    padding: 80px;
    border-bottom: 3px solid var(--black);
}

.schema-section:nth-child(even) { background: var(--white); }

.section-inner { max-width: 1100px; margin: 0 auto; }
```

## ERD Diagram Styles (SVG)

```css
.erd-container {
    background: var(--white);
    border: 3px solid var(--black);
    padding: 40px;
    margin: 32px 0;
    overflow-x: auto;
    box-shadow: 10px 10px 0 var(--black);
}

/* SVG Entity Box */
.entity-box {
    fill: var(--white);
    stroke: var(--black);
    stroke-width: 2;
}

.entity-header {
    fill: var(--black);
}

.entity-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 700;
    fill: var(--white);
}

.entity-column {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    fill: var(--black);
}

.column-pk { font-weight: 700; }
.column-fk { fill: var(--mid-gray); }

/* Relationship Lines */
.relationship-line {
    stroke: var(--black);
    stroke-width: 2;
    fill: none;
}

.relationship-line.one-to-many {
    marker-end: url(#arrow);
}
```

### SVG ERD Template
```html
<svg width="100%" height="600" viewBox="0 0 1000 600">
    <defs>
        <marker id="arrow" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto">
            <path d="M0,0 L0,6 L9,3 z" fill="#1a1a1a"/>
        </marker>
    </defs>
    
    <!-- Entity: users -->
    <g transform="translate(50, 50)">
        <rect class="entity-box" width="180" height="200" rx="0"/>
        <rect class="entity-header" width="180" height="36"/>
        <text class="entity-title" x="90" y="24" text-anchor="middle">users</text>
        <text class="entity-column column-pk" x="12" y="56">🔑 id UUID</text>
        <text class="entity-column" x="12" y="76">phone VARCHAR(20)</text>
        <text class="entity-column" x="12" y="96">name VARCHAR(100)</text>
        <text class="entity-column column-fk" x="12" y="116">🔗 region_id UUID</text>
    </g>
    
    <!-- Relationship line -->
    <path class="relationship-line one-to-many" d="M230,150 L350,150"/>
</svg>
```

## Table Definition Styles

```css
.table-definition {
    background: var(--white);
    border: 2px solid var(--black);
    margin-bottom: 32px;
    box-shadow: 6px 6px 0 var(--black);
}

.table-header {
    background: var(--black);
    color: var(--white);
    padding: 16px 24px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.table-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 18px;
    font-weight: 700;
}

.table-badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 4px 10px;
    border: 1px solid var(--white);
}

.table-description {
    padding: 16px 24px;
    background: var(--bg-gray);
    border-bottom: 2px solid var(--black);
    font-size: 15px;
}

.columns-table {
    width: 100%;
    border-collapse: collapse;
}

.columns-table th {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1px;
    text-align: left;
    padding: 12px 16px;
    background: var(--bg-gray);
    border-bottom: 2px solid var(--black);
}

.columns-table td {
    padding: 12px 16px;
    border-bottom: 1px solid var(--border-gray);
    font-size: 14px;
}

.columns-table tr:last-child td { border-bottom: none; }

.column-name {
    font-family: 'JetBrains Mono', monospace;
    font-weight: 600;
}

.column-type {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--mid-gray);
}

.key-badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    font-weight: 700;
    padding: 3px 8px;
    margin-right: 6px;
}

.key-pk { background: var(--black); color: var(--white); }
.key-fk { background: var(--bg-gray); border: 1px solid var(--black); }
.key-uk { background: var(--white); border: 1px solid var(--mid-gray); color: var(--mid-gray); }
```

## SQL Code Block Styles

```css
.sql-block {
    background: var(--black);
    color: var(--white);
    padding: 24px;
    margin: 20px 0;
    overflow-x: auto;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    line-height: 1.6;
    border: 3px solid var(--black);
    box-shadow: 6px 6px 0 var(--mid-gray);
}

.sql-keyword { color: #fff; font-weight: 700; }
.sql-type { color: #ccc; }
.sql-comment { color: #888; font-style: italic; }
.sql-string { color: #aaa; }
```

## Index Table Styles

```css
.index-table {
    width: 100%;
    border-collapse: collapse;
    margin: 24px 0;
}

.index-table th {
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

.index-table td {
    padding: 14px 16px;
    border: 2px solid var(--black);
    font-size: 14px;
}

.index-name {
    font-family: 'JetBrains Mono', monospace;
    font-weight: 600;
}

.index-type-badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 4px 8px;
    border: 1px solid var(--black);
    display: inline-block;
}
```

## Complete Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Project] - Database Schema</title>
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
            font-size: 16px;
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
            font-size: 12px;
            color: var(--black);
            text-decoration: none;
            border: 2px solid transparent;
            margin-bottom: 4px;
        }
        .nav-link:hover { background: var(--bg-gray); }
        .nav-link.active { background: var(--black); color: var(--white); }
        .nav-number { display: inline-block; width: 32px; font-weight: 600; }
        
        /* Main */
        .main-content { margin-left: 300px; }
        
        .schema-section {
            min-height: 100vh;
            padding: 80px;
            border-bottom: 3px solid var(--black);
        }
        .schema-section:nth-child(even) { background: var(--white); }
        .section-inner { max-width: 1100px; margin: 0 auto; }
        .section-number {
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
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
        
        /* Table Definition */
        .table-definition {
            background: var(--white);
            border: 2px solid var(--black);
            margin-bottom: 32px;
            box-shadow: 6px 6px 0 var(--black);
        }
        .table-header {
            background: var(--black);
            color: var(--white);
            padding: 16px 24px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .table-name {
            font-family: 'JetBrains Mono', monospace;
            font-size: 18px;
            font-weight: 700;
        }
        .table-description {
            padding: 16px 24px;
            background: var(--bg-gray);
            border-bottom: 2px solid var(--black);
            font-size: 15px;
        }
        .columns-table { width: 100%; border-collapse: collapse; }
        .columns-table th {
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-align: left;
            padding: 12px 16px;
            background: var(--bg-gray);
            border-bottom: 2px solid var(--black);
        }
        .columns-table td {
            padding: 12px 16px;
            border-bottom: 1px solid var(--border-gray);
            font-size: 14px;
        }
        .column-name { font-family: 'JetBrains Mono', monospace; font-weight: 600; }
        .column-type { font-family: 'JetBrains Mono', monospace; font-size: 13px; color: var(--mid-gray); }
        .key-badge {
            font-family: 'JetBrains Mono', monospace;
            font-size: 9px;
            font-weight: 700;
            padding: 3px 8px;
            margin-right: 6px;
        }
        .key-pk { background: var(--black); color: var(--white); }
        .key-fk { background: var(--bg-gray); border: 1px solid var(--black); }
        
        /* SQL Block */
        .sql-block {
            background: var(--black);
            color: var(--white);
            padding: 24px;
            margin: 20px 0;
            overflow-x: auto;
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            line-height: 1.6;
            border: 3px solid var(--black);
            box-shadow: 6px 6px 0 var(--mid-gray);
        }
        
        /* ERD */
        .erd-container {
            background: var(--white);
            border: 3px solid var(--black);
            padding: 40px;
            margin: 32px 0;
            overflow-x: auto;
            box-shadow: 10px 10px 0 var(--black);
        }
        
        /* Info Grid */
        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 32px;
        }
        .info-card {
            border: 2px solid var(--black);
            padding: 20px;
            background: var(--white);
        }
        .info-label {
            font-family: 'JetBrains Mono', monospace;
            font-size: 10px;
            text-transform: uppercase;
            color: var(--mid-gray);
            margin-bottom: 8px;
        }
        .info-value {
            font-family: 'JetBrains Mono', monospace;
            font-size: 18px;
            font-weight: 600;
        }
        
        .icon { width: 20px; height: 20px; stroke-width: 2; }
        .icon-sm { width: 16px; height: 16px; }
    </style>
</head>
<body>
    <nav class="sidebar-nav">
        <div class="doc-title">[Project Name]</div>
        <div class="doc-type">Database Schema Design</div>
        <ul class="nav-list">
            <li><a href="#overview" class="nav-link"><span class="nav-number">01</span> Overview</a></li>
            <li><a href="#principles" class="nav-link"><span class="nav-number">02</span> Design Principles</a></li>
            <li><a href="#erd" class="nav-link"><span class="nav-number">03</span> ERD</a></li>
            <li><a href="#schema" class="nav-link"><span class="nav-number">04</span> Schema Definitions</a></li>
            <li><a href="#indexes" class="nav-link"><span class="nav-number">05</span> Indexes</a></li>
            <li><a href="#types" class="nav-link"><span class="nav-number">06</span> Data Types</a></li>
            <li><a href="#partitioning" class="nav-link"><span class="nav-number">07</span> Partitioning</a></li>
            <li><a href="#migration" class="nav-link"><span class="nav-number">08</span> Migrations</a></li>
            <li><a href="#seed" class="nav-link"><span class="nav-number">09</span> Seed Data</a></li>
            <li><a href="#backup" class="nav-link"><span class="nav-number">10</span> Backup & Recovery</a></li>
        </ul>
    </nav>

    <main class="main-content">
        <section id="overview" class="schema-section">
            <div class="section-inner">
                <div class="section-number">Section 01</div>
                <h1 class="section-title">Overview</h1>
                
                <div class="info-grid">
                    <div class="info-card">
                        <div class="info-label">Database</div>
                        <div class="info-value">PostgreSQL 15+</div>
                    </div>
                    <div class="info-card">
                        <div class="info-label">Hosting</div>
                        <div class="info-value">Supabase</div>
                    </div>
                    <div class="info-card">
                        <div class="info-label">Total Tables</div>
                        <div class="info-value">27</div>
                    </div>
                    <div class="info-card">
                        <div class="info-label">Schemas</div>
                        <div class="info-value">4</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Add more sections -->
    </main>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            lucide.createIcons();
        });
    </script>
</body>
</html>
```

## ERD Best Practices

1. **Entity positioning** - Group related entities together
2. **Relationship lines** - Use crow's foot notation for cardinality
3. **Color coding** - PK in black, FK in gray, nullable lighter
4. **Column listing** - Show key columns, truncate long lists with "..."
5. **SVG viewBox** - Make scrollable/zoomable for large schemas

## Output Location
Save schema files to: `/mnt/user-data/outputs/`
