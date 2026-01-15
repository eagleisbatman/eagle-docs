# Eagle Docs for Cursor

Professional documentation generation for Cursor IDE.

Generate PRDs, wireframes, API docs, roadmaps, SWOT analysis, business canvases, and more with customizable themes.

---

## Installation

### Method 1: Copy to Project (Recommended)

```bash
# From your project root
git clone https://github.com/eagleisbatman/eagle-docs.git .eagle-docs-temp
cp -r .eagle-docs-temp/cursor/.cursor .
cp -r .eagle-docs-temp/cursor/docs ./eagle-docs
rm -rf .eagle-docs-temp
```

### Method 2: Manual Installation

1. Download or clone this repository
2. Copy `.cursor/` folder to your project root
3. Copy `docs/` folder to your project as `eagle-docs/`

### Method 3: Symlink (Advanced)

```bash
# Clone once, symlink to multiple projects
git clone https://github.com/eagleisbatman/eagle-docs.git ~/eagle-docs

# In each project
ln -s ~/eagle-docs/cursor/.cursor .cursor
ln -s ~/eagle-docs/cursor/docs eagle-docs
```

---

## Verification

After installation, your project should have:

```
your-project/
├── .cursor/
│   └── rules/
│       ├── 000-eagle-docs-core.mdc
│       ├── 100-prd-design.mdc
│       ├── ... (16 skill files)
│       └── 352-onboarding.mdc
│
└── eagle-docs/
    ├── DESIGN-SYSTEM.md
    ├── QUICK-REFERENCE.md
    └── skills/
        └── ... (16 skill docs)
```

Test with this prompt in Cursor:

```
Create a simple PRD for a login feature using the Material 3 theme.
```

---

## Available Skills (16)

### Product Management
| Skill | Triggers |
|-------|----------|
| PRD Design | PRD, product spec, requirements |
| Roadmap Design | roadmap, timeline, now/next/later |
| Prioritization | RICE, MoSCoW, ICE, Kano |
| Launch Playbook | launch, go-to-market, GTM |

### Strategy & Analysis
| Skill | Triggers |
|-------|----------|
| Strategic Analysis | SWOT, PESTEL, Porter's Five Forces |
| Business Canvas | BMC, Lean Canvas, Value Proposition |
| Analytics Design | KPIs, event tracking, metrics |

### User Research
| Skill | Triggers |
|-------|----------|
| User Research | personas, journey maps, JTBD, empathy maps |

### Design
| Skill | Triggers |
|-------|----------|
| Wireframe Design | wireframes, mockups, UI design |

### Technical Documentation
| Skill | Triggers |
|-------|----------|
| Technical Spec | tech spec, RFC, system design |
| API Spec | API docs, REST API, endpoints |
| Database Schema | database schema, ERD |
| Infrastructure | architecture, deployment, DevOps |

### User-Facing Documentation
| Skill | Triggers |
|-------|----------|
| User Guide | user guide, help docs, tutorials |
| Release Notes | release notes, changelog |
| Onboarding Docs | onboarding, new hire guide |

---

## Themes

| Theme | Style | Best For |
|-------|-------|----------|
| **Brutalist** | Bold black-and-white, harsh shadows | Developer docs |
| **Material 3** | Rounded corners, Google-style | SaaS products |
| **Cupertino** | Apple-style, subtle gradients | Premium products |
| **Modern Minimal** | Clean, whitespace-focused | Startups |

---

## Configuration

Create `.eagle-docs.yaml` in your project root:

```yaml
theme: material  # brutalist | material | cupertino | minimal

colors:
  primary: "#2563EB"
  secondary: "#1E293B"
  accent: "#10B981"

mode: light  # light | dark
```

Or specify in your prompt:

```
Create a SWOT analysis for our mobile app using the Cupertino theme
with primary color #007AFF.
```

---

## How It Works

1. **Core Router** (`000-eagle-docs-core.mdc`) is always loaded
2. Router identifies document type from your request
3. Appropriate skill rule activates (e.g., `100-prd-design.mdc`)
4. Full documentation read from `eagle-docs/skills/`
5. Theme CSS loaded from `eagle-docs/DESIGN-SYSTEM.md`
6. Self-contained HTML generated and saved to `./outputs/`

---

## Output

All documents are saved to `./outputs/` as self-contained HTML files:

- `./outputs/acme-prd.html`
- `./outputs/mobile-app-wireframes.html`
- `./outputs/users-api-docs.html`

Open in any browser - no build step required.

---

## Troubleshooting

### Skills not activating?

Ensure `.cursor/rules/` exists with all `.mdc` files.

### Theme not applying?

Check that `eagle-docs/DESIGN-SYSTEM.md` exists and is readable.

### Missing skill documentation?

Verify `eagle-docs/skills/` contains all 16 `.md` files.

---

## Legacy Mode

If you prefer a single-file setup, copy `.cursorrules` to your project root instead of the `.cursor/rules/` folder. This provides basic routing but less context-efficient.

---

## Links

- [Main Repository](https://github.com/eagleisbatman/eagle-docs)
- [Quick Reference](docs/QUICK-REFERENCE.md)
- [Design System](docs/DESIGN-SYSTEM.md)

---

## Author

**Gautam Mandewalker** ([@eagleisbatman](https://github.com/eagleisbatman))

## License

MIT License
