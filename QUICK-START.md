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

### Content Pipeline Documentation

```
Create content pipeline documentation for [your automated content system].

Pipeline stages:
1. [Stage]: [description]
2. [Stage]: [description]
3. [Stage]: [description]

Data sources: [list APIs/services]
Output format: [audio/video/text/etc.]
Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create content pipeline documentation for an automated podcast system.

Pipeline stages:
1. Data collection: Pull news from RSS feeds and APIs
2. Script generation: Use GPT-4 to write podcast scripts
3. Voice synthesis: Convert scripts to audio via ElevenLabs
4. Post-processing: Add intro/outro, normalize audio
5. Distribution: Upload to Spotify, Apple Podcasts

Data sources: NewsAPI, Weather API, Stock market API
Output format: MP3 audio files (15-20 minutes each)
Theme: Brutalist
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
