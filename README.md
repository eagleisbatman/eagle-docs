# Eagle Docs

**Professional documentation templates for modern teams.**

Eagle Docs is a Claude Code plugin that generates beautiful, consistent HTML documents. Built for product managers, engineers, designers, and technical writers — create professional documentation in minutes, not hours.

---

## Features

- **4 Design Themes** — Brutalist, Material 3, Cupertino, Modern Minimal
- **Custom Brand Colors** — Use your own color palette
- **16 Document Types** — PRDs, roadmaps, SWOT, business canvases, and more
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
Create a SWOT analysis for our mobile app launch.

Context:
- Fintech startup entering payments space
- Competing with established players

Theme: Modern Minimal
Primary color: #2563EB
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

## Available Skills (16)

### Product Management
| Skill | Includes |
|-------|----------|
| **PRD Design** | Product Requirements Documents |
| **Roadmap Design** | Timeline, Now/Next/Later, Theme-based, Release roadmaps |
| **Prioritization Framework** | RICE, MoSCoW, ICE, Value/Effort Matrix, Kano Model |
| **Launch Playbook** | Go-to-market planning, release checklists |

### Strategy & Analysis
| Skill | Includes |
|-------|----------|
| **Strategic Analysis** | PESTEL, SWOT, Porter's Five Forces, Competitive Analysis |
| **Business Canvas** | Business Model Canvas, Lean Canvas, Value Proposition Canvas |
| **Analytics Design** | Event tracking, KPI frameworks, funnel analysis |

### User Research
| Skill | Includes |
|-------|----------|
| **User Research** | Personas, Journey Maps, JTBD, Empathy Maps |

### Design & UI
| Skill | Purpose |
|-------|---------|
| **Wireframe Design** | Low-fidelity UI mockups |

### Technical Documentation
| Skill | Purpose |
|-------|---------|
| **Technical Spec** | Engineering specs, system design, RFCs |
| **API Spec Design** | REST API documentation |
| **Database Schema** | ERD diagrams, table definitions |
| **Infrastructure Design** | Architecture, deployment docs |

### User-Facing Documentation
| Skill | Purpose |
|-------|---------|
| **User Guide** | Help docs, tutorials, how-tos |
| **Release Notes** | Changelogs, version history |
| **Onboarding Docs** | New hire guides, setup docs |

---

## Design Themes

| Theme | Style | Best For |
|-------|-------|----------|
| **Brutalist** | Bold black-and-white, harsh shadows | Developer docs, technical specs |
| **Material 3** | Rounded corners, elevation shadows | Apps, SaaS products |
| **Cupertino** | Subtle gradients, system fonts | iOS/macOS apps, premium products |
| **Modern Minimal** | Clean lines, whitespace | Startups, modern brands |

---

## Who Is This For?

- **Product Managers** — PRDs, roadmaps, prioritization, canvases, analytics
- **Strategists** — SWOT, PESTEL, competitive analysis, business models
- **UX Researchers** — Personas, journey maps, JTBD, empathy maps
- **Software Engineers** — Technical specs, API docs, database schemas
- **Designers** — Wireframes, UI specifications
- **DevOps/SRE** — Infrastructure documentation
- **Technical Writers** — User guides, release notes, help docs
- **Startup Founders** — All of the above, without hiring specialists

---

## File Structure

```
eagle-docs/
├── .claude-plugin/
│   └── plugin.json
├── README.md
├── QUICK-START.md
├── shared/
│   └── DESIGN-SYSTEM.md
│
├── # Product Management
├── prd-design/
├── roadmap-design/
├── prioritization-framework-design/
├── launch-playbook-design/
│
├── # Strategy & Analysis
├── strategic-analysis-design/
├── business-canvas-design/
├── analytics-design/
│
├── # User Research
├── user-research-design/
│
├── # Design
├── wireframe-design/
│
├── # Technical
├── technical-spec-design/
├── api-spec-design/
├── database-schema-design/
├── infrastructure-design/
│
├── # User-Facing
├── user-guide-design/
├── release-notes-design/
└── onboarding-docs-design/
```

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
