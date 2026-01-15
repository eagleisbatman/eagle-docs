# Eagle Docs

**Professional documentation templates for modern teams.**

Eagle Docs is a Claude Code plugin that generates beautiful, consistent HTML documents. Built for product managers, engineers, designers, and technical writers — create professional documentation in minutes, not hours.

---

## Features

- **4 Design Themes** — Brutalist, Material 3, Cupertino, Modern Minimal
- **Custom Brand Colors** — Use your own color palette
- **11 Document Types** — PRDs, wireframes, API docs, technical specs, and more
- **Self-Contained HTML** — No build step, open in any browser
- **Marketplace Ready** — Install via Claude Code plugin system

---

## Installation

### Via Claude Code Marketplace (Recommended)

```bash
# Add the marketplace
/plugin marketplace add eagleisbatman/eagle-docs

# Install the plugin
/plugin install eagle-docs@eagleisbatman
```

### Manual Installation

Clone into your Claude Code skills directory:

```bash
# User-level (available in all projects)
git clone https://github.com/eagleisbatman/eagle-docs.git ~/.claude/skills/eagle-docs

# Or project-level (team sharing)
git clone https://github.com/eagleisbatman/eagle-docs.git .claude/skills/eagle-docs
```

---

## Quick Start

**See [QUICK-START.md](./QUICK-START.md) for copy-paste prompts for each document type.**

### Example

```
Create a PRD for a habit tracking mobile app.

Context:
- Mobile app for iOS and Android
- Target users: Young professionals wanting to build better habits

Theme: Cupertino
Primary color: #5856D6
```

---

## Configuration (Optional)

Create `.eagle-docs.yaml` in your project root:

```yaml
theme: material  # brutalist | material | cupertino | minimal

colors:
  primary: "#2563EB"
  secondary: "#1E293B"
  accent: "#10B981"

mode: light  # light | dark
```

---

## Available Skills

### Product & Planning
| Skill | Purpose | Best For |
|-------|---------|----------|
| **PRD Design** | Product Requirements Documents | PMs, engineers understanding scope |
| **Launch Playbook Design** | Go-to-market & release planning | PMs, release managers |

### Design & UI
| Skill | Purpose | Best For |
|-------|---------|----------|
| **Wireframe Design** | Low-fidelity UI mockups | Designers, PMs, engineers |

### Technical Documentation
| Skill | Purpose | Best For |
|-------|---------|----------|
| **Technical Spec Design** | Engineering specs, system design | Engineers, architects |
| **API Spec Design** | REST API documentation | Backend engineers, integrators |
| **Database Schema Design** | ERD diagrams & table definitions | DBAs, backend engineers |
| **Infrastructure Design** | Architecture & deployment docs | DevOps, SREs |

### Analytics & Data
| Skill | Purpose | Best For |
|-------|---------|----------|
| **Analytics Design** | Event tracking & KPI frameworks | Data engineers, growth teams |

### User-Facing Documentation
| Skill | Purpose | Best For |
|-------|---------|----------|
| **User Guide Design** | Help docs, tutorials, how-tos | Technical writers, PMs |
| **Release Notes Design** | Changelogs, version history | PMs, engineers |
| **Onboarding Docs Design** | New hire guides, setup docs | Engineering leads, HR |

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

## File Structure

```
eagle-docs/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── README.md
├── QUICK-START.md               # Copy-paste prompts
├── shared/
│   └── DESIGN-SYSTEM.md         # Theme specifications
├── prd-design/
├── wireframe-design/
├── database-schema-design/
├── api-spec-design/
├── infrastructure-design/
├── analytics-design/
├── launch-playbook-design/
├── technical-spec-design/
├── user-guide-design/
├── release-notes-design/
└── onboarding-docs-design/
```

---

## Who Is This For?

- **Product Managers** — PRDs, launch playbooks, analytics specs
- **Software Engineers** — Technical specs, API docs, database schemas
- **Designers** — Wireframes, UI specifications
- **DevOps/SRE** — Infrastructure documentation, runbooks
- **Technical Writers** — User guides, release notes, help docs
- **Engineering Leads** — Onboarding docs, team handbooks
- **Startup Founders** — Professional docs without hiring a documentation team

---

## Contributing

Contributions welcome!

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
