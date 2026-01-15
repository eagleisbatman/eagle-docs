# Eagle Docs Design System

**Multi-Theme Documentation Framework**

This design system powers all Eagle Docs skills. It supports multiple visual themes and custom brand colors, ensuring consistency across all generated documentation.

---

## Theme Selection

Before generating any document, determine the user's preferred theme. Check for:

1. **Config file** at `.eagle-docs.yaml` or `eagle-docs.config.json` in the project root
2. **Runtime preference** — Ask the user if no config exists

### Available Themes

| Theme | Best For | Characteristics |
|-------|----------|-----------------|
| **Brutalist** | Technical docs, developer tools | Bold black-and-white, harsh shadows, monospace-heavy |
| **Material 3** | Apps, SaaS products | Rounded corners, elevation, Google's design language |
| **Cupertino** | iOS/macOS apps, premium products | Subtle gradients, SF Pro styling, Apple aesthetics |
| **Modern Minimal** | Startups, clean brands | Generous whitespace, thin lines, elegant simplicity |

---

## Config File Format

Users can create `.eagle-docs.yaml` in their project root:

```yaml
# .eagle-docs.yaml
theme: material  # brutalist | material | cupertino | minimal

colors:
  primary: "#2563EB"      # Main brand color
  secondary: "#1E293B"    # Supporting color
  accent: "#10B981"       # Highlights, CTAs
  background: "#FFFFFF"   # Page background
  surface: "#F8FAFC"      # Card backgrounds
  text: "#0F172A"         # Primary text
  text-muted: "#64748B"   # Secondary text

mode: light  # light | dark

typography:
  heading: "Inter"        # Or: "SF Pro", "Roboto", "JetBrains Mono"
  body: "Inter"           # Or: "SF Pro Text", "Roboto", "IBM Plex Sans"
  mono: "JetBrains Mono"  # For code blocks
```

---

## Theme Specifications

### 1. Brutalist Theme

The original Eagle Docs aesthetic. Bold, unapologetic, technical.

```css
:root {
    /* Colors */
    --color-primary: #1a1a1a;
    --color-secondary: #333333;
    --color-accent: #1a1a1a;
    --color-background: #f5f5f5;
    --color-surface: #ffffff;
    --color-text: #1a1a1a;
    --color-text-muted: #666666;
    --color-border: #1a1a1a;

    /* Shadows */
    --shadow-sm: 4px 4px 0 var(--color-primary);
    --shadow-md: 6px 6px 0 var(--color-primary);
    --shadow-lg: 10px 10px 0 var(--color-primary);

    /* Borders */
    --border-width: 2px;
    --border-style: solid;
    --radius-sm: 0;
    --radius-md: 0;
    --radius-lg: 0;

    /* Typography */
    --font-heading: 'JetBrains Mono', monospace;
    --font-body: 'IBM Plex Sans', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --font-size-base: 16px;
    --line-height: 1.7;
}

/* Brutalist-specific patterns */
.card { box-shadow: var(--shadow-md); }
.btn-primary { background: var(--color-primary); color: white; }
.section:nth-child(even) { background: var(--color-surface); }
.section:nth-child(odd) { background: var(--color-background); }
```

**Font imports:**
```html
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
```

---

### 2. Material 3 Theme

Google's Material Design 3. Modern, accessible, systematic.

```css
:root {
    /* Colors - Material 3 tonal palette */
    --color-primary: #1976D2;
    --color-on-primary: #FFFFFF;
    --color-primary-container: #E3F2FD;
    --color-secondary: #625B71;
    --color-accent: #7C4DFF;
    --color-background: #FFFBFE;
    --color-surface: #FFFFFF;
    --color-surface-variant: #F3EDF7;
    --color-text: #1C1B1F;
    --color-text-muted: #49454F;
    --color-border: #CAC4D0;
    --color-outline: #79747E;

    /* Elevation shadows */
    --shadow-sm: 0 1px 2px rgba(0,0,0,0.3), 0 1px 3px 1px rgba(0,0,0,0.15);
    --shadow-md: 0 1px 2px rgba(0,0,0,0.3), 0 2px 6px 2px rgba(0,0,0,0.15);
    --shadow-lg: 0 4px 8px 3px rgba(0,0,0,0.15), 0 1px 3px rgba(0,0,0,0.3);

    /* Borders */
    --border-width: 1px;
    --border-style: solid;
    --radius-sm: 8px;
    --radius-md: 12px;
    --radius-lg: 16px;
    --radius-xl: 28px;

    /* Typography */
    --font-heading: 'Roboto', sans-serif;
    --font-body: 'Roboto', sans-serif;
    --font-mono: 'Roboto Mono', monospace;
    --font-size-base: 16px;
    --line-height: 1.5;
}

/* Material 3 specific patterns */
.card {
    border-radius: var(--radius-md);
    box-shadow: var(--shadow-md);
    border: none;
}
.btn-primary {
    background: var(--color-primary);
    color: var(--color-on-primary);
    border-radius: var(--radius-xl);
    padding: 10px 24px;
    font-weight: 500;
}
.chip {
    background: var(--color-surface-variant);
    border-radius: 8px;
    padding: 6px 12px;
}
```

**Font imports:**
```html
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&family=Roboto+Mono:wght@400;500&display=swap" rel="stylesheet">
```

---

### 3. Cupertino Theme

Apple's Human Interface Guidelines aesthetic. Premium, subtle, refined.

```css
:root {
    /* Colors - Apple-inspired */
    --color-primary: #007AFF;
    --color-secondary: #5856D6;
    --color-accent: #FF9500;
    --color-background: #F2F2F7;
    --color-surface: #FFFFFF;
    --color-surface-secondary: #F9F9F9;
    --color-text: #000000;
    --color-text-muted: #8E8E93;
    --color-border: #C6C6C8;
    --color-separator: #E5E5EA;

    /* Subtle shadows */
    --shadow-sm: 0 1px 3px rgba(0,0,0,0.08);
    --shadow-md: 0 2px 8px rgba(0,0,0,0.12);
    --shadow-lg: 0 8px 24px rgba(0,0,0,0.15);

    /* Borders */
    --border-width: 0.5px;
    --border-style: solid;
    --radius-sm: 6px;
    --radius-md: 10px;
    --radius-lg: 14px;
    --radius-xl: 20px;

    /* Typography - SF Pro fallback stack */
    --font-heading: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Segoe UI', sans-serif;
    --font-body: -apple-system, BlinkMacSystemFont, 'SF Pro Text', 'Segoe UI', sans-serif;
    --font-mono: 'SF Mono', 'Menlo', monospace;
    --font-size-base: 17px;
    --line-height: 1.47;
    --letter-spacing: -0.022em;
}

/* Cupertino-specific patterns */
.card {
    border-radius: var(--radius-md);
    background: var(--color-surface);
    box-shadow: var(--shadow-sm);
    border: var(--border-width) solid var(--color-separator);
}
.btn-primary {
    background: var(--color-primary);
    color: white;
    border-radius: var(--radius-lg);
    font-weight: 600;
    padding: 12px 20px;
}
.nav-item {
    border-radius: var(--radius-sm);
    transition: background 0.2s ease;
}
.nav-item:hover {
    background: rgba(0,0,0,0.04);
}
```

**No external fonts needed** (uses system fonts)

---

### 4. Modern Minimal Theme

Clean, contemporary, whitespace-focused. Perfect for startups and modern brands.

```css
:root {
    /* Colors - Neutral palette */
    --color-primary: #18181B;
    --color-secondary: #3F3F46;
    --color-accent: #2563EB;
    --color-background: #FFFFFF;
    --color-surface: #FAFAFA;
    --color-text: #18181B;
    --color-text-muted: #71717A;
    --color-border: #E4E4E7;

    /* Minimal shadows */
    --shadow-sm: 0 1px 2px rgba(0,0,0,0.04);
    --shadow-md: 0 4px 6px rgba(0,0,0,0.05);
    --shadow-lg: 0 10px 15px rgba(0,0,0,0.08);

    /* Borders */
    --border-width: 1px;
    --border-style: solid;
    --radius-sm: 4px;
    --radius-md: 6px;
    --radius-lg: 8px;

    /* Typography */
    --font-heading: 'Inter', -apple-system, sans-serif;
    --font-body: 'Inter', -apple-system, sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --font-size-base: 15px;
    --line-height: 1.6;
    --letter-spacing: -0.011em;
}

/* Minimal-specific patterns */
.card {
    border: var(--border-width) solid var(--color-border);
    border-radius: var(--radius-md);
    box-shadow: none;
}
.btn-primary {
    background: var(--color-primary);
    color: white;
    border-radius: var(--radius-sm);
    font-weight: 500;
    padding: 8px 16px;
}
.section {
    border-bottom: 1px solid var(--color-border);
}
h1, h2, h3 {
    letter-spacing: var(--letter-spacing);
}
```

**Font imports:**
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

---

## Custom Color System

When user provides custom colors, apply them to the base theme:

```css
/* User-provided colors override theme defaults */
:root {
    --color-primary: var(--user-primary, #1a1a1a);
    --color-secondary: var(--user-secondary, #333333);
    --color-accent: var(--user-accent, #1a1a1a);
    --color-background: var(--user-background, #f5f5f5);
    --color-surface: var(--user-surface, #ffffff);
    --color-text: var(--user-text, #1a1a1a);
    --color-text-muted: var(--user-text-muted, #666666);
}
```

### Color Contrast Requirements

Always ensure WCAG AA compliance:
- Normal text: 4.5:1 contrast ratio minimum
- Large text (18px+): 3:1 contrast ratio minimum
- UI components: 3:1 contrast ratio minimum

---

## Dark Mode Support

Each theme supports dark mode by inverting the color scheme:

```css
/* Dark mode adjustments */
@media (prefers-color-scheme: dark), [data-theme="dark"] {
    :root {
        --color-background: #0F172A;
        --color-surface: #1E293B;
        --color-text: #F8FAFC;
        --color-text-muted: #94A3B8;
        --color-border: #334155;
    }
}
```

---

## Layout Constants (All Themes)

These remain consistent across all themes:

```css
/* Layout */
--sidebar-width: 280px;
--content-max-width: 900px;
--section-padding: 80px;
--section-min-height: 100vh;

/* Spacing scale */
--space-1: 4px;
--space-2: 8px;
--space-3: 12px;
--space-4: 16px;
--space-5: 20px;
--space-6: 24px;
--space-8: 32px;
--space-10: 40px;
--space-12: 48px;
--space-16: 64px;
--space-20: 80px;
```

---

## Runtime Theme Selection Prompt

When no config file exists, skills should ask:

```
Before generating your document, I need to know your design preferences:

**Theme:** Which visual style?
- Brutalist (bold black-and-white, technical)
- Material 3 (Google's design, rounded)
- Cupertino (Apple-style, refined)
- Modern Minimal (clean, whitespace-focused)

**Colors:** Do you have brand colors?
- Primary color (hex): ______
- Accent color (hex): ______
- Mode: Light / Dark

(Or skip to use theme defaults)
```

---

## Icon Usage (All Themes)

Use Lucide icons consistently:

```html
<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
<script>lucide.createIcons();</script>
```

Common icons:
| Purpose | Icon |
|---------|------|
| Document | `file-text` |
| Database | `database` |
| API | `code` |
| Users | `users` |
| Settings | `settings` |
| Warning | `alert-triangle` |
| Success | `check-circle` |
| Info | `info` |
| Launch | `rocket` |
| Analytics | `bar-chart` |

---

## Output Location

Save generated documents to the current working directory or user-specified path:

```
./outputs/[doc-name].html
```
