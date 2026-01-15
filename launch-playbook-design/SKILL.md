---
name: launch-playbook-design
description: Create professional launch playbook and go-to-market documentation as HTML. Includes launch phases, checklists, success metrics, risk management, rollback procedures, and communication plans. Supports multiple themes (Brutalist, Material 3, Cupertino, Modern Minimal) and custom colors. Outputs are desktop-optimized with one section per viewport. Use when user requests launch plan, GTM strategy, launch playbook, release checklist, or go-live documentation.
---

# Launch Playbook Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional launch playbook documentation as self-contained HTML files. Each section occupies one viewport with scroll-based navigation. Optimized for desktop/laptop viewing (1024px+).

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

1. **Launch Overview** - Vision, principles, phases
2. **Pre-Launch Checklist** - Product, content, technical, operational readiness
3. **Launch Timeline** - Week-by-week breakdown
4. **Soft Launch Strategy** - Alpha, beta, staged rollout
5. **Go-to-Market Strategy** - Channels, messaging, assets
6. **Content Readiness** - Required content, generation pipeline
7. **Technical Readiness** - Infrastructure, load testing, security
8. **Operations Readiness** - On-call, support, monitoring
9. **Launch Day Runbook** - Hour-by-hour procedures
10. **Post-Launch Monitoring** - Metrics, dashboards, alerts
11. **Rollback Procedures** - Scenarios, commands, recovery
12. **Success Metrics** - KPIs, targets, measurement
13. **Risk Management** - Risk register, contingencies, kill switches
14. **Communication Plan** - Internal, external, crisis comms

## Special Components

### Phase Timeline Visualization
```css
.phase-timeline {
    display: flex;
    gap: 0;
    margin: 32px 0;
}

.phase-block {
    flex: 1;
    padding: 24px;
    border: 2px solid var(--black);
    border-right: none;
    position: relative;
}

.phase-block:last-child { border-right: 2px solid var(--black); }

.phase-block.active {
    background: var(--black);
    color: var(--white);
}

.phase-number {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1px;
    opacity: 0.7;
    margin-bottom: 8px;
}

.phase-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 16px;
    font-weight: 700;
    margin-bottom: 12px;
}

.phase-details {
    font-size: 14px;
}
```

### Checklist Style
```css
.checklist {
    background: var(--white);
    border: 2px solid var(--black);
    box-shadow: 6px 6px 0 var(--black);
}

.checklist-header {
    background: var(--black);
    color: var(--white);
    padding: 16px 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.checklist-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 700;
}

.checklist-progress {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
}

.checklist-item {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 16px 20px;
    border-bottom: 1px solid var(--border-gray);
}

.checklist-item:last-child { border-bottom: none; }

.checkbox {
    width: 24px;
    height: 24px;
    border: 2px solid var(--black);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
}

.checkbox.checked {
    background: var(--black);
    color: var(--white);
}

.checklist-text {
    font-size: 15px;
    flex: 1;
}

.checklist-status {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 4px 10px;
    border: 1px solid var(--black);
}
```

### Runbook Command Block
```css
.runbook-step {
    background: var(--white);
    border: 2px solid var(--black);
    margin-bottom: 20px;
}

.runbook-step-header {
    background: var(--bg-gray);
    padding: 16px 20px;
    display: flex;
    align-items: center;
    gap: 16px;
    border-bottom: 2px solid var(--black);
}

.step-number {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 700;
    width: 36px;
    height: 36px;
    background: var(--black);
    color: var(--white);
    display: flex;
    align-items: center;
    justify-content: center;
}

.step-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 15px;
    font-weight: 600;
}

.step-time {
    margin-left: auto;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--mid-gray);
}

.runbook-command {
    background: #1a1a1a;
    color: #f5f5f5;
    padding: 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    overflow-x: auto;
}
```

### Risk Matrix
```css
.risk-card {
    border: 2px solid var(--black);
    margin-bottom: 16px;
    display: grid;
    grid-template-columns: auto 1fr auto auto;
    align-items: center;
}

.risk-severity {
    padding: 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    writing-mode: vertical-lr;
    text-orientation: mixed;
    transform: rotate(180deg);
}

.risk-high { background: var(--black); color: var(--white); }
.risk-medium { background: var(--bg-gray); }
.risk-low { background: var(--white); color: var(--mid-gray); }

.risk-content { padding: 16px 20px; }

.risk-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 15px;
    font-weight: 600;
    margin-bottom: 8px;
}

.risk-mitigation {
    font-size: 14px;
    color: var(--mid-gray);
}

.risk-probability, .risk-impact {
    padding: 16px;
    text-align: center;
    border-left: 2px solid var(--black);
}

.prob-label, .impact-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    text-transform: uppercase;
    color: var(--mid-gray);
    margin-bottom: 4px;
}

.prob-value, .impact-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 700;
}
```

## Complete Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Project] - Launch Playbook</title>
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
            font-size: 11px;
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
        
        .launch-section {
            min-height: 100vh;
            padding: 80px;
            border-bottom: 3px solid var(--black);
        }
        .launch-section:nth-child(even) { background: var(--white); }
        .section-inner { max-width: 1000px; margin: 0 auto; }
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
        
        /* Phase Timeline */
        .phase-timeline { display: flex; gap: 0; margin: 32px 0; }
        .phase-block {
            flex: 1;
            padding: 24px;
            border: 2px solid var(--black);
            border-right: none;
        }
        .phase-block:last-child { border-right: 2px solid var(--black); }
        .phase-block.active { background: var(--black); color: var(--white); }
        .phase-number {
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            text-transform: uppercase;
            opacity: 0.7;
            margin-bottom: 8px;
        }
        .phase-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 15px;
            font-weight: 700;
            margin-bottom: 12px;
        }
        .phase-details { font-size: 13px; line-height: 1.6; }
        
        /* Checklist */
        .checklist {
            background: var(--white);
            border: 2px solid var(--black);
            margin-bottom: 24px;
            box-shadow: 6px 6px 0 var(--black);
        }
        .checklist-header {
            background: var(--black);
            color: var(--white);
            padding: 14px 20px;
            display: flex;
            justify-content: space-between;
        }
        .checklist-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            font-weight: 700;
        }
        .checklist-item {
            display: flex;
            align-items: flex-start;
            gap: 16px;
            padding: 14px 20px;
            border-bottom: 1px solid var(--border-gray);
        }
        .checkbox {
            width: 22px; height: 22px;
            border: 2px solid var(--black);
            flex-shrink: 0;
        }
        .checkbox.checked { background: var(--black); }
        .checklist-text { font-size: 14px; }
        
        /* Metrics Grid */
        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 20px;
            margin: 32px 0;
        }
        .metric-card {
            border: 2px solid var(--black);
            padding: 24px;
            text-align: center;
            background: var(--white);
        }
        .metric-value {
            font-family: 'JetBrains Mono', monospace;
            font-size: 32px;
            font-weight: 700;
        }
        .metric-label {
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            text-transform: uppercase;
            color: var(--mid-gray);
            margin-top: 8px;
        }
        .metric-target {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            color: var(--mid-gray);
            margin-top: 4px;
        }
        
        /* Risk Card */
        .risk-card {
            border: 2px solid var(--black);
            margin-bottom: 16px;
            display: flex;
        }
        .risk-severity {
            padding: 16px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 10px;
            font-weight: 700;
            text-transform: uppercase;
            writing-mode: vertical-lr;
            transform: rotate(180deg);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .risk-high { background: var(--black); color: var(--white); }
        .risk-medium { background: var(--bg-gray); }
        .risk-low { background: var(--white); color: var(--mid-gray); }
        .risk-content { padding: 16px 20px; flex: 1; }
        .risk-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 6px;
        }
        .risk-mitigation { font-size: 14px; color: var(--mid-gray); }
        
        .icon { width: 20px; height: 20px; stroke-width: 2; }
    </style>
</head>
<body>
    <nav class="sidebar-nav">
        <div class="doc-title">[Project Name]</div>
        <div class="doc-type">Launch Playbook</div>
        <ul class="nav-list">
            <li><a href="#overview" class="nav-link"><span class="nav-number">01</span> Overview</a></li>
            <li><a href="#checklist" class="nav-link"><span class="nav-number">02</span> Pre-Launch</a></li>
            <li><a href="#timeline" class="nav-link"><span class="nav-number">03</span> Timeline</a></li>
            <li><a href="#soft-launch" class="nav-link"><span class="nav-number">04</span> Soft Launch</a></li>
            <li><a href="#gtm" class="nav-link"><span class="nav-number">05</span> GTM Strategy</a></li>
            <li><a href="#runbook" class="nav-link"><span class="nav-number">06</span> Launch Day</a></li>
            <li><a href="#monitoring" class="nav-link"><span class="nav-number">07</span> Monitoring</a></li>
            <li><a href="#rollback" class="nav-link"><span class="nav-number">08</span> Rollback</a></li>
            <li><a href="#metrics" class="nav-link"><span class="nav-number">09</span> Success Metrics</a></li>
            <li><a href="#risks" class="nav-link"><span class="nav-number">10</span> Risks</a></li>
        </ul>
    </nav>

    <main class="main-content">
        <section id="overview" class="launch-section">
            <div class="section-inner">
                <div class="section-number">Section 01</div>
                <h1 class="section-title">Launch Overview</h1>
                
                <div class="phase-timeline">
                    <div class="phase-block">
                        <div class="phase-number">Phase 0</div>
                        <div class="phase-title">Internal Alpha</div>
                        <div class="phase-details">2 weeks<br>50 users<br>Bug discovery</div>
                    </div>
                    <div class="phase-block active">
                        <div class="phase-number">Phase 1</div>
                        <div class="phase-title">Closed Beta</div>
                        <div class="phase-details">4 weeks<br>1,000 users<br>Product-market fit</div>
                    </div>
                    <div class="phase-block">
                        <div class="phase-number">Phase 2</div>
                        <div class="phase-title">Open Beta</div>
                        <div class="phase-details">4 weeks<br>10,000 users<br>Scale testing</div>
                    </div>
                    <div class="phase-block">
                        <div class="phase-number">Phase 3</div>
                        <div class="phase-title">GA Launch</div>
                        <div class="phase-details">Ongoing<br>Unlimited<br>Growth</div>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="metrics" class="launch-section">
            <div class="section-inner">
                <div class="section-number">Section 09</div>
                <h1 class="section-title">Success Metrics</h1>
                
                <div class="metrics-grid">
                    <div class="metric-card">
                        <div class="metric-value">99.5%</div>
                        <div class="metric-label">Uptime</div>
                        <div class="metric-target">Target: Must Have</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value">&gt;45%</div>
                        <div class="metric-label">D1 Retention</div>
                        <div class="metric-target">Target: Week 1</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value">&gt;30%</div>
                        <div class="metric-label">D7 Retention</div>
                        <div class="metric-target">Target: Week 4</div>
                    </div>
                    <div class="metric-card">
                        <div class="metric-value">&gt;3.5</div>
                        <div class="metric-label">App Rating</div>
                        <div class="metric-target">Target: Week 1</div>
                    </div>
                </div>
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
Save launch playbook files to: `/mnt/user-data/outputs/`
