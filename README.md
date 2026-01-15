# Eagle Docs

**Professional documentation templates for modern teams.**

Eagle Docs is a collection of battle-tested documentation skills that generate beautiful, consistent HTML documents. Built for Claude Code, these skills help product managers, engineers, designers, and technical writers create professional documentation in minutes, not hours.

---

## Features

- **4 Design Themes** — Brutalist, Material 3, Cupertino, Modern Minimal
- **Custom Brand Colors** — Use your own color palette
- **8 Document Types** — PRDs, wireframes, API docs, database schemas, and more
- **Self-Contained HTML** — No build step, open in any browser
- **One Section Per Viewport** — Clean, scroll-based navigation

---

## Quick Start

**See [QUICK-START.md](./QUICK-START.md) for copy-paste prompts for each document type.**

### Example Prompt

```
Create a PRD for a habit tracking mobile app.

Context:
- Mobile app for iOS and Android
- Target users: Young professionals wanting to build better habits

Theme: Cupertino
Primary color: #5856D6
```

---

## Installation

### Option 1: Project-Level (Recommended for Teams)

Clone into your project's `.claude/skills/` directory:

```bash
git clone https://github.com/eagleisbatman/eagle-docs.git .claude/skills/eagle-docs
```

Skills will be automatically discovered for this project.

### Option 2: User-Level (Personal Use)

Clone into your global Claude Code skills directory:

```bash
git clone https://github.com/eagleisbatman/eagle-docs.git ~/.claude/skills/eagle-docs
```

Skills will be available across all your projects.

---

## Configuration (Optional)

Create `.eagle-docs.yaml` in your project root to set default preferences:

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

mode: light  # light | dark

typography:
  heading: "Inter"
  body: "Inter"
  mono: "JetBrains Mono"
```

If no config file exists, you can specify preferences in your prompt or Claude will ask you.

---

## Available Skills

| Skill | Purpose | Best For |
|-------|---------|----------|
| **PRD Design** | Product Requirements Documents | PMs defining features, engineers understanding scope |
| **Wireframe Design** | Low-fidelity UI mockups | Designers, PMs, engineers aligning on UI |
| **Database Schema Design** | ERD diagrams & table definitions | Backend engineers, architects, DBAs |
| **API Spec Design** | REST API documentation | Backend engineers, API consumers, integrators |
| **Infrastructure Design** | Architecture & deployment docs | DevOps, SREs, platform engineers |
| **Analytics Design** | Event tracking & KPI frameworks | Data engineers, PMs, growth teams |
| **Content Pipeline Design** | AI content generation workflows | ML engineers, content automation teams |
| **Launch Playbook Design** | Go-to-market & release planning | PMs, engineering leads, release managers |

---

## Design Themes

### Brutalist
Bold black-and-white with harsh shadows. Technical, developer-focused aesthetic.

### Material 3
Google's Material Design 3. Rounded corners, elevation shadows, systematic spacing.

### Cupertino
Apple Human Interface Guidelines aesthetic. Subtle gradients, system fonts, refined.

### Modern Minimal
Clean lines, generous whitespace, contemporary feel. Perfect for startups.

---

## Who Is This For?

**Everyone who writes technical documentation:**

- **Product Managers** — PRDs, launch playbooks, analytics specs
- **Software Engineers** — API docs, database schemas, infrastructure designs
- **Designers** — Wireframes, UI specifications
- **DevOps/SRE** — Infrastructure documentation, runbooks
- **Technical Writers** — Consistent templates for any technical content
- **Startup Founders** — Professional docs without hiring a documentation team

---

## File Structure

```
eagle-docs/
├── README.md
├── QUICK-START.md              # Copy-paste prompts
├── shared/
│   └── DESIGN-SYSTEM.md        # Theme specs & color system
├── prd-design/
│   └── SKILL.md
├── wireframe-design/
│   └── SKILL.md
├── database-schema-design/
│   └── SKILL.md
├── api-spec-design/
│   └── SKILL.md
├── infrastructure-design/
│   └── SKILL.md
├── analytics-design/
│   └── SKILL.md
├── content-pipeline-design/
│   └── SKILL.md
└── launch-playbook-design/
    └── SKILL.md
```

---

## Output

All documents are generated as self-contained HTML files:

```
./outputs/[document-name].html
```

- Open directly in any browser
- No build step required
- Print-ready
- Easy to share

---

## Contributing

Contributions welcome! Ideas for improvements:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## Author

**Gautam Mandewalker** ([@eagleisbatman](https://github.com/eagleisbatman))

---

## License

MIT License — Use freely, attribution appreciated.
