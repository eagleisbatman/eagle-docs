---
name: infrastructure-design
description: Create professional infrastructure and architecture documentation as HTML. Includes system diagrams, cloud service configurations, cost estimates, monitoring setup, and disaster recovery plans. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Outputs are desktop-optimized with one section per viewport. Use when user requests infrastructure documentation, architecture diagram, cloud setup guide, DevOps documentation, or deployment guide.
---

# Infrastructure Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional infrastructure documentation as self-contained HTML files. Each section occupies one viewport with scroll-based navigation. Optimized for desktop/laptop viewing (1024px+).

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

## Document Structure (Required Sections)

1. **Overview** - Design principles, traffic projections, tech stack
2. **Architecture Summary** - Component inventory, data flow patterns
3. **Cloud Services** - Service configurations (CDN, Storage, etc.)
4. **Compute Infrastructure** - Servers, containers, scaling
5. **Database Layer** - DB setup, connection pooling, caching
6. **Caching Strategy** - Cache layers, TTLs, invalidation
7. **Monitoring & Observability** - Logging, metrics, alerts
8. **Security Configuration** - Auth, secrets, WAF
9. **Disaster Recovery** - Backup, failover, RTO/RPO
10. **Cost Estimates** - By service, by scale tier

## Architecture Diagram Style (SVG)

```html
<svg viewBox="0 0 1000 600" class="arch-diagram">
    <!-- Layer labels -->
    <text x="20" y="40" class="layer-label">CLIENT LAYER</text>
    
    <!-- Service boxes -->
    <g class="service-box" transform="translate(100, 60)">
        <rect width="120" height="60" fill="#fff" stroke="#1a1a1a" stroke-width="2"/>
        <text x="60" y="35" text-anchor="middle" class="service-name">Service</text>
    </g>
    
    <!-- Arrows/connections -->
    <path d="M220,90 L280,90" stroke="#1a1a1a" stroke-width="2" marker-end="url(#arrow)"/>
    
    <!-- Arrow marker -->
    <defs>
        <marker id="arrow" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto">
            <path d="M0,0 L0,6 L9,3 z" fill="#1a1a1a"/>
        </marker>
    </defs>
</svg>
```

## Complete Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Project] - Infrastructure Guide</title>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        :root {
            --black: #1a1a1a;
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
            padding: 10px 16px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            color: var(--black);
            text-decoration: none;
            border: 2px solid transparent;
            margin-bottom: 2px;
        }
        .nav-link:hover { background: var(--bg-gray); }
        .nav-link.active { background: var(--black); color: var(--white); }
        .nav-number { display: inline-block; width: 28px; font-weight: 600; }
        
        /* Main */
        .main-content { margin-left: 300px; }
        
        .infra-section {
            min-height: 100vh;
            padding: 80px;
            border-bottom: 3px solid var(--black);
        }
        .infra-section:nth-child(even) { background: var(--white); }
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
        
        /* Architecture Diagram */
        .arch-diagram-container {
            background: var(--white);
            border: 3px solid var(--black);
            padding: 40px;
            margin: 32px 0;
            box-shadow: 10px 10px 0 var(--black);
            overflow-x: auto;
        }
        .arch-diagram { width: 100%; min-height: 400px; }
        .layer-label {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            font-weight: 700;
            letter-spacing: 2px;
            fill: var(--mid-gray);
        }
        .service-name {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            font-weight: 600;
        }
        .service-desc {
            font-family: 'IBM Plex Sans', sans-serif;
            font-size: 10px;
            fill: var(--mid-gray);
        }
        
        /* Service Cards */
        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 24px;
            margin: 32px 0;
        }
        .service-card {
            background: var(--white);
            border: 2px solid var(--black);
            box-shadow: 6px 6px 0 var(--black);
        }
        .service-card-header {
            background: var(--black);
            color: var(--white);
            padding: 14px 20px;
            display: flex;
            align-items: center;
            gap: 12px;
        }
        .service-card-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 14px;
            font-weight: 700;
        }
        .service-card-body { padding: 20px; }
        .service-detail {
            display: flex;
            justify-content: space-between;
            padding: 8px 0;
            border-bottom: 1px solid var(--border-gray);
            font-size: 14px;
        }
        .service-detail:last-child { border-bottom: none; }
        .detail-label {
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            color: var(--mid-gray);
        }
        .detail-value {
            font-family: 'JetBrains Mono', monospace;
            font-weight: 600;
        }
        
        /* Cost Table */
        .cost-table { width: 100%; border-collapse: collapse; margin: 24px 0; }
        .cost-table th {
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            text-transform: uppercase;
            text-align: left;
            padding: 14px;
            background: var(--black);
            color: var(--white);
            border: 2px solid var(--black);
        }
        .cost-table td {
            padding: 14px;
            border: 2px solid var(--black);
            font-size: 14px;
        }
        .cost-table tr:nth-child(even) { background: var(--bg-gray); }
        .cost-total {
            font-family: 'JetBrains Mono', monospace;
            font-weight: 700;
            background: var(--black) !important;
            color: var(--white);
        }
        
        /* Config Blocks */
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
        .config-header {
            color: var(--light-gray);
            margin-bottom: 12px;
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        /* Metric Cards */
        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 16px;
            margin: 24px 0;
        }
        .metric-card {
            border: 2px solid var(--black);
            padding: 20px;
            text-align: center;
            background: var(--white);
        }
        .metric-value {
            font-family: 'JetBrains Mono', monospace;
            font-size: 28px;
            font-weight: 700;
        }
        .metric-label {
            font-family: 'JetBrains Mono', monospace;
            font-size: 10px;
            text-transform: uppercase;
            color: var(--mid-gray);
            margin-top: 8px;
        }
        
        .icon { width: 20px; height: 20px; stroke-width: 2; }
        .icon-sm { width: 16px; height: 16px; }
    </style>
</head>
<body>
    <nav class="sidebar-nav">
        <div class="doc-title">[Project Name]</div>
        <div class="doc-type">Infrastructure Guide</div>
        <ul class="nav-list">
            <li><a href="#overview" class="nav-link"><span class="nav-number">01</span> Overview</a></li>
            <li><a href="#architecture" class="nav-link"><span class="nav-number">02</span> Architecture</a></li>
            <li><a href="#cloud" class="nav-link"><span class="nav-number">03</span> Cloud Services</a></li>
            <li><a href="#compute" class="nav-link"><span class="nav-number">04</span> Compute</a></li>
            <li><a href="#database" class="nav-link"><span class="nav-number">05</span> Database</a></li>
            <li><a href="#caching" class="nav-link"><span class="nav-number">06</span> Caching</a></li>
            <li><a href="#monitoring" class="nav-link"><span class="nav-number">07</span> Monitoring</a></li>
            <li><a href="#security" class="nav-link"><span class="nav-number">08</span> Security</a></li>
            <li><a href="#dr" class="nav-link"><span class="nav-number">09</span> Disaster Recovery</a></li>
            <li><a href="#costs" class="nav-link"><span class="nav-number">10</span> Costs</a></li>
        </ul>
    </nav>

    <main class="main-content">
        <section id="overview" class="infra-section">
            <div class="section-inner">
                <div class="section-number">Section 01</div>
                <h1 class="section-title">Overview</h1>
                
                <div class="metrics-grid">
                    <div class="metric-card">
                        <div class="metric-value">99.9%</div>
                        <div class="metric-label">Target Uptime</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value">&lt;100ms</div>
                        <div class="metric-label">P95 Latency</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value">1M+</div>
                        <div class="metric-label">Users Scale</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value">$800</div>
                        <div class="metric-label">Monthly Cost</div>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="architecture" class="infra-section">
            <div class="section-inner">
                <div class="section-number">Section 02</div>
                <h1 class="section-title">Architecture Summary</h1>
                
                <div class="arch-diagram-container">
                    <svg class="arch-diagram" viewBox="0 0 900 400">
                        <!-- Example diagram structure -->
                        <defs>
                            <marker id="arrow" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto">
                                <path d="M0,0 L0,6 L9,3 z" fill="#1a1a1a"/>
                            </marker>
                        </defs>
                        
                        <text x="20" y="30" class="layer-label">CLIENT LAYER</text>
                        <rect x="20" y="45" width="860" height="70" fill="none" stroke="#ddd" stroke-width="1" stroke-dasharray="4"/>
                        
                        <text x="20" y="150" class="layer-label">EDGE LAYER</text>
                        <rect x="20" y="165" width="860" height="70" fill="none" stroke="#ddd" stroke-width="1" stroke-dasharray="4"/>
                        
                        <text x="20" y="270" class="layer-label">APPLICATION LAYER</text>
                        <rect x="20" y="285" width="860" height="70" fill="none" stroke="#ddd" stroke-width="1" stroke-dasharray="4"/>
                    </svg>
                </div>
            </div>
        </section>
        
        <section id="costs" class="infra-section">
            <div class="section-inner">
                <div class="section-number">Section 10</div>
                <h1 class="section-title">Cost Estimates</h1>
                
                <table class="cost-table">
                    <thead>
                        <tr>
                            <th>Service</th>
                            <th>Component</th>
                            <th>Unit Cost</th>
                            <th>Usage</th>
                            <th>Monthly</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Cloudflare</td>
                            <td>Pro Plan</td>
                            <td>$20/mo</td>
                            <td>1</td>
                            <td>$20</td>
                        </tr>
                        <tr>
                            <td>Cloudflare</td>
                            <td>R2 Storage</td>
                            <td>$0.015/GB</td>
                            <td>500 GB</td>
                            <td>$7.50</td>
                        </tr>
                        <tr class="cost-total">
                            <td colspan="4">Total</td>
                            <td>$791/mo</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>
    </main>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            lucide.createIcons();
        });
    </script>
</body>
</html>
```

## Output Location
Save infrastructure docs to: `/mnt/user-data/outputs/`
