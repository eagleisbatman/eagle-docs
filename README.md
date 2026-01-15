# Eagle Docs

**Professional documentation templates for modern teams.**

Eagle Docs is a collection of battle-tested documentation skills that generate beautiful, consistent HTML documents with a distinctive brutalist black-and-white aesthetic. Built for Claude Code, these skills help product managers, engineers, designers, and technical writers create professional documentation in minutes, not hours.

---

## What's Inside

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

## Design Philosophy

All Eagle Docs outputs share a consistent design language:

- **Brutalist aesthetic** — Bold black-and-white styling, no unnecessary decoration
- **One section per viewport** — Each section is designed to fill exactly one screen
- **Scroll-based navigation** — Smooth, predictable navigation through documents
- **Desktop-optimized** — Built for the screens where real work happens
- **Print-ready** — Clean output that looks great when printed or exported

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

## How It Works

Eagle Docs skills are designed for [Claude Code](https://claude.ai/claude-code). Each skill:

1. Takes your requirements as natural language input
2. Generates a complete HTML document with proper structure
3. Applies consistent brutalist styling automatically
4. Outputs a single, self-contained HTML file

### Example Usage

```
You: Create a PRD for a user authentication system with OAuth support

Claude: [Generates a complete PRD with sections for overview, user stories,
        technical requirements, success metrics, and more]
```

---

## File Structure

```
eagle-docs/
├── README.md
├── shared/
│   └── DESIGN-SYSTEM.md          # Shared styling & components
├── prd-design/
│   └── SKILL.md                  # Product Requirements Documents
├── wireframe-design/
│   └── SKILL.md                  # UI Wireframes & Mockups
├── database-schema-design/
│   └── SKILL.md                  # Database ERDs & Schemas
├── api-spec-design/
│   └── SKILL.md                  # API Documentation
├── infrastructure-design/
│   └── SKILL.md                  # Architecture & Infrastructure
├── analytics-design/
│   └── SKILL.md                  # Analytics & Event Tracking
├── content-pipeline-design/
│   └── SKILL.md                  # AI Content Generation Pipelines
└── launch-playbook-design/
    └── SKILL.md                  # Launch & GTM Planning
```

---

## Installation

### For Claude Code Users

1. Clone this repository:
   ```bash
   git clone https://github.com/eagleisbatman/eagle-docs.git
   ```

2. Copy the skills to your Claude Code skills directory:
   ```bash
   cp -r eagle-docs/* ~/.claude/skills/
   ```

3. Restart Claude Code — the skills will be automatically detected.

### Manual Usage

Each `SKILL.md` file contains the complete prompt and styling guidelines. You can use these directly with any LLM by copying the skill content into your conversation.

---

## Contributing

Contributions are welcome! If you have ideas for new documentation types or improvements to existing skills:

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
