# Brutalist Technical Documentation Design System

**Shared Reference for All Document Skills**

## Core Design Tokens

```css
:root {
    /* Colors - Grayscale Only */
    --black: #1a1a1a;
    --dark-gray: #333333;
    --mid-gray: #666666;
    --light-gray: #999999;
    --border-gray: #dddddd;
    --bg-gray: #f5f5f5;
    --white: #ffffff;
}
```

## Typography

```css
/* Font Import */
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&display=swap');

/* Usage */
- JetBrains Mono: Headers, labels, code, technical text
- IBM Plex Sans: Body text, descriptions, paragraphs

/* Sizes (LARGER than typical) */
- Body: 16-17px, line-height 1.7
- Section titles: 32px
- Subsection titles: 20-24px
- Labels: 12-14px uppercase
- Code: 13-14px
- Annotations: 14-15px minimum
```

## Layout Principles

1. **One Section Per Viewport**
   - min-height: 100vh
   - padding: 80px
   - Scroll to navigate

2. **Sticky Sidebar Navigation**
   - width: 280-300px
   - position: fixed
   - Numbered sections (01, 02, 03...)

3. **Content Container**
   - margin-left: 280-300px
   - max-width: 900-1100px per section
   - Centered within main area

## Component Patterns

### Cards with Shadow
```css
.card {
    background: var(--white);
    border: 2px solid var(--black);
    padding: 24-32px;
    box-shadow: 6px 6px 0 var(--black);
    /* or larger: 8px 8px 0, 10px 10px 0 */
}
```

### Section Dividers
```css
.section {
    border-bottom: 3px solid var(--black);
}
.section:nth-child(even) {
    background: var(--white);
}
.section:nth-child(odd) {
    background: var(--bg-gray);
}
```

### Tables
```css
.table th {
    background: var(--black);
    color: var(--white);
    font-family: 'JetBrains Mono';
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1px;
}
.table td {
    border: 2px solid var(--black);
    padding: 12-16px;
}
```

### Badges/Tags
```css
.badge {
    font-family: 'JetBrains Mono';
    font-size: 9-11px;
    font-weight: 700;
    text-transform: uppercase;
    padding: 4px 10px;
    border: 2px solid var(--black);
}
.badge-filled {
    background: var(--black);
    color: var(--white);
}
```

### Code Blocks
```css
.code-block {
    background: #1a1a1a;
    color: #f5f5f5;
    font-family: 'JetBrains Mono';
    font-size: 13px;
    padding: 20-24px;
    border: 2px solid var(--black);
    box-shadow: 6px 6px 0 var(--mid-gray);
}
```

## Required HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Doc Title]</title>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        /* ... styles ... */
    </style>
</head>
<body>
    <nav class="sidebar-nav">
        <!-- Sticky navigation -->
    </nav>
    <main class="main-content">
        <section id="section-1" class="doc-section">
            <div class="section-inner">
                <div class="section-number">Section 01</div>
                <h1 class="section-title">Title</h1>
                <!-- Content -->
            </div>
        </section>
        <!-- More sections -->
    </main>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            lucide.createIcons();
            // Active nav highlighting script
        });
    </script>
</body>
</html>
```

## Icon Usage (Lucide)

Common icons for technical docs:
- `file-text` - Documents
- `database` - Database
- `server` - Infrastructure
- `code` - API/Code
- `git-branch` - Versioning
- `shield` - Security
- `clock` - Timeline
- `alert-triangle` - Warnings/Risks
- `check-circle` - Success/Checkmarks
- `settings` - Configuration
- `layers` - Architecture
- `zap` - Performance
- `users` - User personas
- `target` - Goals
- `bar-chart` - Analytics
- `rocket` - Launch
