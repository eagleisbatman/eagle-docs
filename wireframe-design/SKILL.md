---
name: wireframe-design-v2
description: Create high-quality black-and-white mobile and web wireframes with proper Lucide icons, brutalist styling, and comprehensive annotations. Outputs are HTML documents optimized for desktop/laptop viewing with one screen per viewport and scroll-based navigation. Use when user requests wireframes, mockups, UI designs, or says "black and white" or "low fidelity" design.
---

# Wireframe Design Skill v2

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional, black-and-white wireframes as HTML documents. Each screen occupies one viewport height with scroll-based navigation. Optimized for desktop/laptop viewing (1024px+).

## Key Changes from v1
- **One screen per viewport** - No cramped horizontal layouts
- **Larger fonts** - 16px base, 14px minimum for annotations
- **Sticky navigation** - TOC sidebar for quick jumping
- **Desktop-first** - Optimized for laptop/desktop screens

## Technical Setup

### Required Imports
```html
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
```

### Color Palette (Grayscale Only)
```css
:root {
    --black: #1a1a1a;
    --dark-gray: #333333;
    --mid-gray: #666666;
    --light-gray: #999999;
    --border-gray: #dddddd;
    --bg-gray: #f5f5f5;
    --white: #ffffff;
    /* Status colors - use sparingly */
    --status-success: #080;
    --status-warning: #f90;
    --status-error: #c00;
}
```

## Layout Structure

### Page Layout (Desktop-First)
```css
body {
    font-family: 'IBM Plex Sans', sans-serif;
    font-size: 16px;
    line-height: 1.6;
    background: var(--bg-gray);
    color: var(--black);
    margin: 0;
    padding: 0;
}

.page-container {
    display: flex;
    min-height: 100vh;
}

/* Sticky sidebar navigation */
.sidebar-nav {
    width: 280px;
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    background: var(--white);
    border-right: 2px solid var(--black);
    padding: 24px;
    overflow-y: auto;
    z-index: 100;
}

/* Main content area */
.main-content {
    margin-left: 280px;
    flex: 1;
    padding: 0;
}
```

### Screen Section (One Per Viewport)
```css
.screen-section {
    min-height: 100vh;
    padding: 48px 64px;
    border-bottom: 3px solid var(--black);
    display: flex;
    gap: 48px;
    align-items: flex-start;
    background: var(--bg-gray);
}

.screen-section:nth-child(even) {
    background: var(--white);
}
```

### Phone Frame (Centered in Viewport)
```css
.phone-frame {
    width: 390px;
    min-width: 390px;
    background: var(--white);
    border: 3px solid var(--black);
    border-radius: 32px;
    overflow: hidden;
    box-shadow: 12px 12px 0 var(--black);
}

.phone-header {
    background: var(--black);
    color: var(--white);
    padding: 16px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 600;
}

.phone-content {
    padding: 20px;
    min-height: 700px;
    position: relative;
    padding-bottom: 80px;
}
```

### Annotations Panel (LARGER FONTS)
```css
.annotation-panel {
    flex: 1;
    max-width: 500px;
}

.annotation-card {
    background: var(--white);
    border: 2px solid var(--black);
    padding: 24px;
    margin-bottom: 24px;
    box-shadow: 6px 6px 0 var(--black);
}

.annotation-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 16px;
    padding-bottom: 12px;
    border-bottom: 2px solid var(--black);
}

.annotation-list {
    font-size: 15px;
    line-height: 1.8;
}

.annotation-list li {
    margin-bottom: 12px;
    padding-left: 8px;
}

.annotation-note {
    font-size: 14px;
    color: var(--mid-gray);
    font-style: italic;
    margin-top: 16px;
    padding-top: 16px;
    border-top: 1px dashed var(--border-gray);
}
```

## Sidebar Navigation

```css
.sidebar-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 20px;
    font-weight: 700;
    margin-bottom: 8px;
}

.sidebar-subtitle {
    font-size: 13px;
    color: var(--mid-gray);
    margin-bottom: 32px;
    padding-bottom: 16px;
    border-bottom: 2px solid var(--black);
}

.nav-list {
    list-style: none;
    padding: 0;
    margin: 0;
}

.nav-item {
    margin-bottom: 4px;
}

.nav-link {
    display: block;
    padding: 12px 16px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--black);
    text-decoration: none;
    border: 2px solid transparent;
    transition: all 0.15s ease;
}

.nav-link:hover {
    background: var(--bg-gray);
    border-color: var(--black);
}

.nav-link.active {
    background: var(--black);
    color: var(--white);
}

.nav-number {
    display: inline-block;
    width: 28px;
    font-weight: 600;
}
```

## UI Components (Larger Sizes)

### Typography
```css
.page-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 28px;
    font-weight: 700;
    border-bottom: 4px solid var(--black);
    padding-bottom: 12px;
    margin-bottom: 24px;
}

.section-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 16px;
}

.card-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 15px;
    font-weight: 600;
    margin-bottom: 8px;
}

.body-text {
    font-size: 15px;
    line-height: 1.6;
}

.label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    color: var(--mid-gray);
}
```

### Buttons
```css
.btn {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    padding: 12px 20px;
    border: 2px solid var(--black);
    background: var(--white);
    display: inline-flex;
    align-items: center;
    gap: 8px;
    cursor: pointer;
}

.btn-primary {
    background: var(--black);
    color: var(--white);
}

.btn-lg {
    font-size: 14px;
    padding: 14px 24px;
}
```

### Cards
```css
.card {
    border: 2px solid var(--black);
    padding: 16px;
    margin-bottom: 16px;
    background: var(--white);
}

.card-highlight {
    border-left: 4px solid var(--black);
    background: var(--bg-gray);
}
```

### Bottom Navigation
```css
.bottom-nav {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    border-top: 2px solid var(--black);
    background: var(--white);
}

.bottom-nav-item {
    flex: 1;
    padding: 14px 12px;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
}

.bottom-nav-item.active {
    background: var(--black);
    color: var(--white);
}

.bottom-nav-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}
```

### Icons
```css
.icon { width: 22px; height: 22px; stroke-width: 2; }
.icon-sm { width: 18px; height: 18px; stroke-width: 2; }
.icon-lg { width: 26px; height: 26px; stroke-width: 2; }
```

## Complete Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[App Name] - Wireframes</title>
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
            line-height: 1.6;
            background: var(--bg-gray);
            color: var(--black);
        }
        
        /* Sidebar Navigation */
        .sidebar-nav {
            width: 280px;
            position: fixed;
            top: 0;
            left: 0;
            height: 100vh;
            background: var(--white);
            border-right: 3px solid var(--black);
            padding: 32px 24px;
            overflow-y: auto;
            z-index: 100;
        }
        .sidebar-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 4px;
        }
        .sidebar-subtitle {
            font-size: 13px;
            color: var(--mid-gray);
            margin-bottom: 32px;
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
        .nav-number { display: inline-block; width: 32px; font-weight: 600; }
        
        /* Main Content */
        .main-content { margin-left: 280px; }
        
        /* Screen Sections */
        .screen-section {
            min-height: 100vh;
            padding: 64px;
            border-bottom: 3px solid var(--black);
            display: flex;
            gap: 64px;
            align-items: flex-start;
            justify-content: center;
        }
        .screen-section:nth-child(even) { background: var(--white); }
        
        /* Phone Frame */
        .phone-frame {
            width: 390px;
            min-width: 390px;
            background: var(--white);
            border: 3px solid var(--black);
            border-radius: 32px;
            overflow: hidden;
            box-shadow: 12px 12px 0 var(--black);
        }
        .phone-header {
            background: var(--black);
            color: var(--white);
            padding: 16px 20px;
            display: flex;
            align-items: center;
            gap: 12px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 14px;
            font-weight: 600;
        }
        .phone-content {
            padding: 20px;
            min-height: 680px;
            position: relative;
            padding-bottom: 80px;
        }
        
        /* Annotation Panel */
        .annotation-panel { flex: 1; max-width: 480px; }
        .annotation-card {
            background: var(--white);
            border: 2px solid var(--black);
            padding: 28px;
            margin-bottom: 24px;
            box-shadow: 6px 6px 0 var(--black);
        }
        .annotation-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 20px;
            padding-bottom: 12px;
            border-bottom: 2px solid var(--black);
        }
        .annotation-list {
            font-size: 15px;
            line-height: 1.9;
            padding-left: 20px;
        }
        .annotation-list li { margin-bottom: 12px; }
        .annotation-note {
            font-size: 14px;
            color: var(--mid-gray);
            margin-top: 20px;
            padding-top: 16px;
            border-top: 1px dashed var(--border-gray);
            font-style: italic;
        }
        
        /* Components */
        .icon { width: 22px; height: 22px; stroke-width: 2; }
        .icon-sm { width: 18px; height: 18px; }
        .section-label {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--mid-gray);
            margin-bottom: 12px;
        }
        .card {
            border: 2px solid var(--black);
            padding: 16px;
            margin-bottom: 12px;
            background: var(--white);
        }
        .card-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 6px;
        }
        .card-text { font-size: 14px; color: var(--mid-gray); }
        .btn {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            padding: 12px 20px;
            border: 2px solid var(--black);
            background: var(--white);
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        .btn-primary { background: var(--black); color: var(--white); }
        .bottom-nav {
            position: absolute;
            bottom: 0; left: 0; right: 0;
            display: flex;
            border-top: 2px solid var(--black);
            background: var(--white);
        }
        .bottom-nav-item {
            flex: 1;
            padding: 14px 8px;
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 6px;
        }
        .bottom-nav-item.active { background: var(--black); color: var(--white); }
        .bottom-nav-label {
            font-family: 'JetBrains Mono', monospace;
            font-size: 10px;
            text-transform: uppercase;
        }
    </style>
</head>
<body>
    <!-- Sidebar Navigation -->
    <nav class="sidebar-nav">
        <div class="sidebar-title">[App Name]</div>
        <div class="sidebar-subtitle">Wireframes • [N] Screens</div>
        <ul class="nav-list">
            <li><a href="#screen-1" class="nav-link"><span class="nav-number">01</span> Screen Name</a></li>
            <li><a href="#screen-2" class="nav-link"><span class="nav-number">02</span> Screen Name</a></li>
            <!-- Add more screens -->
        </ul>
    </nav>

    <!-- Main Content -->
    <main class="main-content">
        <!-- Screen 1 -->
        <section id="screen-1" class="screen-section">
            <div class="phone-frame">
                <div class="phone-header">
                    <i data-lucide="home" class="icon-sm"></i>
                    <span>Screen Title</span>
                </div>
                <div class="phone-content">
                    <!-- Screen content here -->
                    
                    <div class="bottom-nav">
                        <div class="bottom-nav-item active">
                            <i data-lucide="home" class="icon-sm"></i>
                            <span class="bottom-nav-label">Home</span>
                        </div>
                        <div class="bottom-nav-item">
                            <i data-lucide="search" class="icon-sm"></i>
                            <span class="bottom-nav-label">Search</span>
                        </div>
                        <div class="bottom-nav-item">
                            <i data-lucide="user" class="icon-sm"></i>
                            <span class="bottom-nav-label">Profile</span>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="annotation-panel">
                <div class="annotation-card">
                    <div class="annotation-title">Screen: [Name]</div>
                    <ul class="annotation-list">
                        <li><strong>Purpose:</strong> Brief description of screen purpose</li>
                        <li><strong>Entry points:</strong> How users arrive here</li>
                        <li><strong>Key actions:</strong> Primary user actions</li>
                        <li><strong>Exit points:</strong> Where users go next</li>
                    </ul>
                    <div class="annotation-note">
                        Design note: Any special considerations for implementation
                    </div>
                </div>
            </div>
        </section>

        <!-- Screen 2 -->
        <section id="screen-2" class="screen-section">
            <!-- Same structure as Screen 1 -->
        </section>
    </main>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            lucide.createIcons();
            
            // Highlight current section in nav
            const sections = document.querySelectorAll('.screen-section');
            const navLinks = document.querySelectorAll('.nav-link');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => link.classList.remove('active'));
                        const activeLink = document.querySelector(`a[href="#${entry.target.id}"]`);
                        if (activeLink) activeLink.classList.add('active');
                    }
                });
            }, { threshold: 0.5 });
            
            sections.forEach(section => observer.observe(section));
        });
    </script>
</body>
</html>
```

## Common Icon Reference

| Concept | Icon Name |
|---------|-----------|
| Home | `home` |
| Search | `search` |
| User/Profile | `user` |
| Settings | `settings` |
| Menu | `menu` |
| Back | `arrow-left` |
| Forward | `chevron-right` |
| Add | `plus` |
| Edit | `edit` |
| Delete | `trash-2` |
| Download | `download` |
| Play | `play` |
| Pause | `pause` |
| Check | `check` |
| Close | `x` |
| Bell/Notification | `bell` |
| Calendar | `calendar` |
| Clock | `clock` |
| Location | `map-pin` |
| Star | `star` |

## Best Practices

1. **One screen per viewport** - Never stack multiple screens horizontally
2. **Generous whitespace** - 64px padding, 48px+ gaps
3. **Large annotations** - 15px font minimum, 1.9 line-height
4. **Sticky sidebar** - Always visible navigation
5. **Numbered screens** - Clear sequence (01, 02, 03...)
6. **Consistent structure** - Same layout pattern for all screens
7. **Lucide icons only** - Never use emojis
8. **Grayscale only** - Status colors sparingly

## Output Location
Save wireframe files to: `/mnt/user-data/outputs/`
