# Eagle Docs Quick Reference

Quick lookup for all 16 documentation skills.

---

## Product Management

| Skill | Trigger Words | Output |
|-------|---------------|--------|
| **PRD Design** | PRD, product spec, requirements document, feature spec | Product Requirements Document |
| **Roadmap Design** | roadmap, timeline, now/next/later, release plan | Product Roadmap |
| **Prioritization** | RICE, MoSCoW, ICE, Kano, prioritization, value/effort | Prioritization Framework |
| **Launch Playbook** | launch, go-to-market, GTM, release checklist | Launch Playbook |

---

## Strategy & Analysis

| Skill | Trigger Words | Output |
|-------|---------------|--------|
| **Strategic Analysis** | SWOT, PESTEL, Porter's Five Forces, competitive analysis | Strategic Analysis |
| **Business Canvas** | Business Model Canvas, BMC, Lean Canvas, Value Proposition | Business Canvas |
| **Analytics Design** | analytics, KPIs, event tracking, metrics, funnel | Analytics Framework |

---

## User Research

| Skill | Trigger Words | Output |
|-------|---------------|--------|
| **User Research** | persona, journey map, JTBD, empathy map, user insights | User Research Document |

---

## Design

| Skill | Trigger Words | Output |
|-------|---------------|--------|
| **Wireframe Design** | wireframe, mockup, UI design, low-fidelity, screens | Wireframe Document |

---

## Technical Documentation

| Skill | Trigger Words | Output |
|-------|---------------|--------|
| **Technical Spec** | tech spec, RFC, system design, engineering spec | Technical Specification |
| **API Spec** | API docs, REST API, endpoints, OpenAPI | API Documentation |
| **Database Schema** | database schema, ERD, table definitions, data model | Database Schema |
| **Infrastructure** | infrastructure, architecture, deployment, DevOps | Infrastructure Document |

---

## User-Facing Documentation

| Skill | Trigger Words | Output |
|-------|---------------|--------|
| **User Guide** | user guide, help docs, tutorial, how-to | User Guide |
| **Release Notes** | release notes, changelog, what's new, version history | Release Notes |
| **Onboarding Docs** | onboarding, new hire guide, setup guide | Onboarding Document |

---

## Themes

| Theme | Style | Best For |
|-------|-------|----------|
| **Brutalist** | Bold black-and-white, harsh shadows, sharp corners | Developer docs, technical specs |
| **Material 3** | Rounded corners, elevation shadows, Google-style | Apps, SaaS products |
| **Cupertino** | Subtle gradients, system fonts, Apple-style | iOS/macOS apps, premium products |
| **Modern Minimal** | Clean lines, whitespace, contemporary | Startups, modern brands |

---

## Config File (.eagle-docs.yaml)

```yaml
theme: material  # brutalist | material | cupertino | minimal

colors:
  primary: "#2563EB"
  secondary: "#1E293B"
  accent: "#10B981"

mode: light  # light | dark
```

---

## Output Location

All documents save to: `./outputs/[name]-[type].html`

Examples:
- `./outputs/acme-prd.html`
- `./outputs/mobile-app-wireframes.html`
- `./outputs/users-api-docs.html`
