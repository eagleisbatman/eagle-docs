# Eagle Docs Quick Start Guide

Copy-paste prompts to generate professional documentation instantly.

---

## Before You Start

### Option 1: Set Up Config (Recommended)

Create `.eagle-docs.yaml` in your project root:

```yaml
theme: material  # brutalist | material | cupertino | minimal
colors:
  primary: "#2563EB"
  accent: "#10B981"
mode: light
```

### Option 2: Specify at Runtime

Include your preferences in the prompt:

```
Theme: Material 3
Primary color: #2563EB
Accent: #10B981
```

---

## Quick Start Prompts

### PRD (Product Requirements Document)

```
Create a PRD for [your feature/product name].

Context:
- [Brief description of what you're building]
- [Target users]
- [Key problem being solved]

Theme: [brutalist/material/cupertino/minimal]
Primary color: [hex code or skip for defaults]
```

**Example:**
```
Create a PRD for a habit tracking mobile app.

Context:
- Mobile app for iOS and Android
- Target users: Young professionals (25-35) wanting to build better habits
- Key problem: Existing habit apps are too complex and don't provide accountability

Theme: Cupertino
Primary color: #5856D6
```

---

### Wireframes

```
Create wireframes for [your app/feature name].

Screens needed:
1. [Screen name + brief description]
2. [Screen name + brief description]
3. [Screen name + brief description]

Platform: [mobile/web/both]
Theme: [brutalist/material/cupertino/minimal]
Primary color: [hex code or skip]
```

**Example:**
```
Create wireframes for an e-commerce checkout flow.

Screens needed:
1. Cart review - Show items, quantities, totals
2. Shipping info - Address form with saved addresses
3. Payment - Card entry with Apple Pay/Google Pay options
4. Confirmation - Order summary and tracking info

Platform: mobile
Theme: Material 3
```

---

### Database Schema

```
Create database schema documentation for [your project/system].

Entities:
- [Entity 1]: [brief description]
- [Entity 2]: [brief description]
- [Entity 3]: [brief description]

Database: [PostgreSQL/MySQL/MongoDB/etc.]
Include: [ERD diagram / migration scripts / seed data]
Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create database schema documentation for a multi-tenant SaaS platform.

Entities:
- Organizations: Company accounts with billing info
- Users: Team members with roles and permissions
- Projects: Work containers with settings
- Tasks: Individual work items with assignments

Database: PostgreSQL (Supabase)
Include: ERD diagram, migration scripts, RLS policies
Theme: Brutalist
```

---

### API Documentation

```
Create API documentation for [your API name].

Endpoints:
- [Method] [Path]: [Description]
- [Method] [Path]: [Description]
- [Method] [Path]: [Description]

Auth: [JWT/API Key/OAuth/etc.]
Base URL: [your API base URL]
Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create API documentation for a task management API.

Endpoints:
- POST /auth/login: Authenticate user and return JWT
- GET /tasks: List all tasks for current user
- POST /tasks: Create a new task
- PATCH /tasks/:id: Update task details
- DELETE /tasks/:id: Delete a task

Auth: JWT with refresh tokens
Base URL: https://api.taskapp.io/v1
Theme: Modern Minimal
Primary color: #18181B
```

---

### Infrastructure Documentation

```
Create infrastructure documentation for [your project/system].

Stack:
- [Service 1]: [purpose]
- [Service 2]: [purpose]
- [Service 3]: [purpose]

Requirements:
- Target uptime: [percentage]
- Expected scale: [users/requests]
- Budget: [monthly estimate]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create infrastructure documentation for a real-time collaboration app.

Stack:
- Vercel: Frontend hosting (Next.js)
- Supabase: Database and auth
- Cloudflare: CDN and edge functions
- Upstash: Redis for real-time features

Requirements:
- Target uptime: 99.9%
- Expected scale: 100K DAU
- Budget: $500/month initial

Theme: Brutalist
```

---

### Analytics Framework

```
Create analytics documentation for [your product].

Key metrics:
- [Metric 1]: [definition]
- [Metric 2]: [definition]
- [Metric 3]: [definition]

Key events:
- [Event 1]: [when triggered]
- [Event 2]: [when triggered]

Analytics stack: [Mixpanel/Amplitude/PostHog/etc.]
Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create analytics documentation for a subscription news app.

Key metrics:
- WAU (Weekly Active Users): Unique users who opened app in last 7 days
- Article completion rate: % of articles read to the end
- Subscription conversion: Free to paid conversion rate

Key events:
- article_viewed: User opens an article
- article_completed: User scrolls to article end
- subscription_started: User completes payment

Analytics stack: Mixpanel
Theme: Modern Minimal
```

---

### Launch Playbook

```
Create a launch playbook for [your product/feature].

Launch type: [new product / major feature / update]
Timeline: [target launch date or duration]

Phases:
- [Phase 1]: [description]
- [Phase 2]: [description]

Success metrics:
- [Metric]: [target]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a launch playbook for a mobile app public launch.

Launch type: New product (v1.0 public release)
Timeline: 4 weeks to launch

Phases:
- Week 1-2: Internal testing with 50 employees
- Week 3: Closed beta with 500 waitlist users
- Week 4: Public launch on App Store and Play Store

Success metrics:
- Week 1 DAU: 10,000
- D1 retention: >40%
- App store rating: >4.0

Theme: Material 3
Primary color: #1976D2
```

---

### Technical Spec

```
Create a technical spec for [your feature/system].

Context:
- Problem: [what problem are you solving]
- Scope: [what's included]
- Constraints: [technical constraints]

Include: [architecture diagram / API design / data model]
Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a technical spec for a real-time notification system.

Context:
- Problem: Users miss important updates because we only have email notifications
- Scope: Web push, mobile push, and in-app notifications
- Constraints: Must work offline, max 100ms delivery latency

Include: Architecture diagram, API design, data model
Theme: Brutalist
```

---

### User Guide

```
Create a user guide for [your product/feature].

Sections needed:
- [Section 1]
- [Section 2]
- [Section 3]

Audience: [who will read this]
Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a user guide for a project management app.

Sections needed:
- Getting started (account setup, first project)
- Managing tasks (create, assign, track)
- Team collaboration (invites, comments, mentions)
- Integrations (Slack, GitHub, Calendar)

Audience: Non-technical team leads and project managers
Theme: Material 3
Primary color: #1976D2
```

---

### Release Notes

```
Create release notes for [product] version [X.X.X].

Changes:
- New: [feature 1], [feature 2]
- Improved: [enhancement 1]
- Fixed: [bug 1], [bug 2]
- Breaking: [breaking change if any]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create release notes for TaskApp version 2.5.0.

Changes:
- New: Dark mode support, keyboard shortcuts, bulk task editing
- Improved: Search now 3x faster, better mobile responsiveness
- Fixed: Calendar sync issues, notification delays on Android
- Breaking: Dropped support for iOS 14

Theme: Modern Minimal
```

---

### Onboarding Documentation

```
Create onboarding documentation for [team/company].

Include:
- [Section 1]
- [Section 2]
- [Section 3]

Audience: [new engineers / new employees / contractors]
Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create onboarding documentation for new backend engineers.

Include:
- Day 1 checklist (accounts, hardware, introductions)
- Development environment setup (Docker, IDE, local DB)
- Codebase overview (architecture, key services, conventions)
- First week goals (first PR, shadow on-call, meet stakeholders)

Audience: New backend engineers joining the platform team
Theme: Material 3
Primary color: #1976D2
```

---

## Product Management Frameworks

### Prioritization Framework (RICE, MoSCoW, etc.)

```
Create a prioritization framework for [your backlog/features].

Framework: [RICE / MoSCoW / ICE / Value-Effort Matrix / Kano]

Items to prioritize:
- [Feature 1]
- [Feature 2]
- [Feature 3]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a RICE scoring prioritization for our Q2 feature backlog.

Framework: RICE

Items to prioritize:
- Dark mode support
- Social sharing features
- Offline mode
- Advanced search filters
- Push notifications
- Multi-language support

Theme: Modern Minimal
Primary color: #18181B
```

---

### Business Canvas

```
Create a [Business Model Canvas / Lean Canvas / Value Proposition Canvas] for [company/product].

Context:
- [Brief description]
- [Target market]
- [Key differentiator]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a Lean Canvas for a B2B SaaS analytics platform.

Context:
- Self-serve analytics for small businesses
- Target market: SMBs with 10-100 employees
- Key differentiator: No-code dashboard builder

Theme: Material 3
Primary color: #1976D2
```

---

### Strategic Analysis (SWOT, PESTEL, Porter's)

```
Create a [SWOT / PESTEL / Porter's Five Forces / Competitive Analysis] for [company/product].

Context:
- Industry: [industry]
- Market position: [description]
- Key competitors: [list]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a SWOT analysis for our fintech startup.

Context:
- Industry: Digital payments
- Market position: New entrant in peer-to-peer payments
- Key competitors: Venmo, Cash App, Zelle

Theme: Brutalist
```

---

### User Research (Personas, Journey Maps, JTBD)

```
Create [user personas / journey map / JTBD / empathy map] for [product/service].

User segment: [description]
Research basis: [interviews, surveys, data]

Include:
- [Specific elements to cover]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create user personas for a fitness tracking app.

User segments:
1. Casual fitness enthusiast (walks, light workouts)
2. Serious athlete (training plans, competitions)
3. Health-conscious professional (busy schedule, desk job)

Include: Demographics, goals, pain points, behaviors, tech savviness
Theme: Cupertino
Primary color: #007AFF
```

---

### Product Roadmap

```
Create a [timeline / now-next-later / theme-based / release] roadmap for [product].

Time horizon: [e.g., Q1-Q4 2025]
Teams/Themes: [list]

Key initiatives:
- [Initiative 1]
- [Initiative 2]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a Now/Next/Later roadmap for our mobile app.

Time horizon: Next 6 months

Now (committed):
- Performance optimization
- Bug fixes from v2.0 launch

Next (planned):
- Dark mode
- Social features
- Widget support

Later (exploratory):
- AI recommendations
- Wearable integration

Theme: Material 3
Primary color: #2563EB
```

---

## Plan Mode Workflow

For complex documents, use plan mode for better results:

```
Enter plan mode. I need to create [document type] for [project].

First, establish my design system:
- Theme: [preference]
- Colors: Primary [hex], Accent [hex]
- Mode: [light/dark]

Then create the document with these requirements:
[Your specific requirements]
```

This ensures the design system is locked in before generation begins, maintaining consistency even if the context compacts during long sessions.

---

## Tips for Best Results

1. **Be specific** — The more context you provide, the better the output
2. **Use examples** — Include sample data where relevant
3. **Specify audience** — Who will read this document?
4. **Set constraints** — Page limits, must-have sections, etc.
5. **Request iterations** — Ask for specific section improvements after first draft

---

## Output

All documents are saved as self-contained HTML files to:
```
./outputs/[document-name].html
```

Open directly in any browser. No build step required.
