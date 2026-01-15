# Eagle Docs Quick Start Guide

Complete prompt library for all 16 documentation skills.

---

## Table of Contents

1. [Installation](#installation)
2. [Configuration](#configuration)
3. [Product Management](#product-management)
4. [Strategy & Analysis](#strategy--analysis)
5. [User Research](#user-research)
6. [Design](#design)
7. [Technical Documentation](#technical-documentation)
8. [User-Facing Documentation](#user-facing-documentation)
9. [Composite Workflows](#composite-workflows)
10. [Tips & Best Practices](#tips--best-practices)

---

## Installation

### Method 1: Claude Code Marketplace (Recommended)

```bash
# Step 1: Add the Eagle Docs marketplace
/plugin marketplace add eagleisbatman/eagle-docs

# Step 2: Install the plugin
/plugin install eagle-docs@eagleisbatman

# Step 3: Verify installation
/plugin list
```

### Method 2: Interactive Plugin Manager

```bash
# Open the plugin manager UI
/plugin

# Then:
# 1. Go to "Marketplaces" tab
# 2. Click "Add Marketplace"
# 3. Enter: eagleisbatman/eagle-docs
# 4. Go to "Discover" tab
# 5. Find "Eagle Docs" and click "Install"
```

### Method 3: Manual Installation (Git Clone)

```bash
# Option A: User-level (available in all your projects)
git clone https://github.com/eagleisbatman/eagle-docs.git ~/.claude/skills/eagle-docs

# Option B: Project-level (shared with team via git)
git clone https://github.com/eagleisbatman/eagle-docs.git .claude/skills/eagle-docs
```

### Method 4: Direct Download

1. Go to https://github.com/eagleisbatman/eagle-docs
2. Click "Code" → "Download ZIP"
3. Extract to `~/.claude/skills/eagle-docs`

### Verify Installation

After installation, the skills will be automatically discovered. You can test by asking:

```
Create a simple PRD for a login feature.
```

---

## Configuration

### Option 1: Config File (Recommended for Teams)

Create `.eagle-docs.yaml` in your project root:

```yaml
# .eagle-docs.yaml - Eagle Docs Configuration

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
  heading: "Inter"
  body: "Inter"
  mono: "JetBrains Mono"
```

### Option 2: Specify in Prompt

Add these lines to any prompt:

```
Theme: Material 3
Primary color: #2563EB
Accent color: #10B981
Mode: light
```

### Option 3: Let Claude Ask

Simply run the skill without specifying theme — Claude will ask for your preferences.

---

## Product Management

### PRD (Product Requirements Document)

**Basic PRD:**
```
Create a PRD for [feature/product name].

Context:
- [What you're building]
- [Target users]
- [Problem being solved]
```

**Detailed PRD:**
```
Create a comprehensive PRD for [feature name].

Product: [Product name]
Target release: [Quarter/Date]

Problem Statement:
[Describe the problem in 2-3 sentences]

Target Users:
- Primary: [User segment]
- Secondary: [User segment]

Success Metrics:
- [Metric 1]: [Target]
- [Metric 2]: [Target]

Constraints:
- Technical: [Any technical limitations]
- Timeline: [Deadline constraints]
- Budget: [Resource constraints]

Theme: [brutalist/material/cupertino/minimal]
```

**Example - Mobile App Feature:**
```
Create a PRD for a social sharing feature in our fitness app.

Product: FitTrack Mobile App
Target release: Q2 2025

Problem Statement:
Users want to share their workout achievements with friends but currently have to screenshot and manually post. This friction reduces engagement and viral growth.

Target Users:
- Primary: Active users who complete 3+ workouts/week
- Secondary: New users in first 30 days

Success Metrics:
- Share rate: 15% of completed workouts shared
- Viral coefficient: 0.3 new users per share
- D7 retention of referred users: >40%

Constraints:
- Must work offline (queue shares)
- Support Instagram, Twitter, Facebook
- No increase in app size >2MB

Theme: Cupertino
Primary color: #FF2D55
```

**Example - B2B SaaS Feature:**
```
Create a PRD for role-based access control (RBAC) in our project management SaaS.

Product: TeamFlow
Target release: Q1 2025

Problem Statement:
Enterprise customers need granular permissions to comply with SOC2 and internal security policies. Currently we only have Admin/Member roles which blocks enterprise deals.

Target Users:
- Primary: IT admins at companies 500+ employees
- Secondary: Team leads managing sensitive projects

Success Metrics:
- Enterprise deal close rate: +25%
- Support tickets about permissions: -50%
- Time to configure permissions: <10 minutes

Theme: Modern Minimal
```

---

### Product Roadmap

**Now/Next/Later Roadmap:**
```
Create a Now/Next/Later roadmap for [product].

Now (committed, in progress):
- [Feature 1]
- [Feature 2]

Next (planned, next quarter):
- [Feature 3]
- [Feature 4]

Later (exploring, future):
- [Feature 5]
- [Feature 6]

Theme: [brutalist/material/cupertino/minimal]
```

**Timeline Roadmap:**
```
Create a quarterly timeline roadmap for [product].

Time horizon: [Q1-Q4 2025]

Swimlanes:
- [Team/Theme 1]
- [Team/Theme 2]
- [Team/Theme 3]

Initiatives:
Q1:
- [Initiative]: [Team] - [Description]

Q2:
- [Initiative]: [Team] - [Description]

Milestones:
- [Date]: [Milestone name]

Theme: [brutalist/material/cupertino/minimal]
```

**Theme-Based Roadmap:**
```
Create a theme-based roadmap for [product].

Strategic Themes:

Theme 1: [Name] - [Goal]
- [Initiative 1]
- [Initiative 2]

Theme 2: [Name] - [Goal]
- [Initiative 1]
- [Initiative 2]

Theme: [brutalist/material/cupertino/minimal]
```

**Release Roadmap:**
```
Create a release roadmap for [product].

Releases:

v2.1 (Target: [Date])
- [Feature 1]
- [Feature 2]
Status: [In Progress/Planned]

v2.2 (Target: [Date])
- [Feature 3]
- [Feature 4]
Status: [Planned]

v3.0 (Target: [Date])
- [Major feature]
Status: [Exploratory]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a Now/Next/Later roadmap for our e-commerce platform.

Now (committed):
- Checkout redesign (improving conversion)
- Apple Pay / Google Pay integration
- Performance optimization (target: <2s load time)

Next (Q2):
- Wishlist functionality
- Product recommendations engine
- Multi-currency support

Later (H2):
- AR try-on for fashion items
- Social shopping features
- Subscription/recurring orders

Theme: Material 3
Primary color: #1976D2
```

---

### Prioritization Framework

**RICE Scoring:**
```
Create a RICE prioritization for [backlog/features].

Items to score:
1. [Feature]: Reach [X users], Impact [0.25-3], Confidence [50-100%], Effort [person-months]
2. [Feature]: ...
3. [Feature]: ...

Or let me estimate - just list features:
- [Feature 1]
- [Feature 2]
- [Feature 3]

Theme: [brutalist/material/cupertino/minimal]
```

**MoSCoW Prioritization:**
```
Create a MoSCoW prioritization for [release/sprint].

Features to categorize:
- [Feature 1]
- [Feature 2]
- [Feature 3]
- [Feature 4]
- [Feature 5]

Context: [Release constraints, deadline, resources]

Theme: [brutalist/material/cupertino/minimal]
```

**Value vs Effort Matrix:**
```
Create a Value/Effort matrix for [backlog].

Items to plot:
- [Feature 1]: Value [H/M/L], Effort [H/M/L]
- [Feature 2]: Value [H/M/L], Effort [H/M/L]
- [Feature 3]: ...

Theme: [brutalist/material/cupertino/minimal]
```

**ICE Scoring:**
```
Create an ICE scoring prioritization for [features].

Items (I'll estimate Impact, Confidence, Ease 1-10):
- [Feature 1]
- [Feature 2]
- [Feature 3]

Theme: [brutalist/material/cupertino/minimal]
```

**Kano Model:**
```
Create a Kano model analysis for [product features].

Features to categorize (Must-have/Performance/Delighter/Indifferent):
- [Feature 1]
- [Feature 2]
- [Feature 3]

Based on: [User research/surveys/assumptions]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a RICE prioritization for our mobile app Q2 backlog.

Items to score:
1. Push notifications: Reach 50K users, Impact 2 (high), Confidence 80%, Effort 1 month
2. Dark mode: Reach 50K users, Impact 1 (medium), Confidence 90%, Effort 0.5 months
3. Offline mode: Reach 10K users, Impact 3 (massive), Confidence 60%, Effort 3 months
4. Social sharing: Reach 20K users, Impact 2 (high), Confidence 70%, Effort 1 month
5. Advanced filters: Reach 5K users, Impact 1 (medium), Confidence 90%, Effort 0.5 months

Theme: Brutalist
```

---

### Launch Playbook

**Product Launch:**
```
Create a launch playbook for [product/feature].

Launch type: [New product / Major feature / Minor update]
Target date: [Date]

Phases:
- Alpha: [Users, duration, goals]
- Beta: [Users, duration, goals]
- GA: [Strategy]

Success metrics:
- [Metric]: [Target]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a launch playbook for our mobile app public launch.

Launch type: New product (v1.0)
Target date: March 15, 2025

Phases:
- Internal alpha (2 weeks): 50 employees, find critical bugs
- Closed beta (3 weeks): 500 waitlist users, validate core flows
- Soft launch (1 week): 5,000 users in test market (Canada)
- Public launch: App Store + Play Store worldwide

Success metrics:
- Week 1 DAU: 10,000
- D1 retention: >45%
- Crash-free rate: >99.5%
- App store rating: >4.0

Risks:
- Server capacity for launch spike
- App store review delays
- Negative early reviews

Theme: Material 3
Primary color: #2563EB
```

---

## Strategy & Analysis

### SWOT Analysis

**Basic SWOT:**
```
Create a SWOT analysis for [company/product].

Context:
- Industry: [industry]
- Company stage: [startup/growth/mature]
- Key competitors: [list]
```

**Detailed SWOT:**
```
Create a comprehensive SWOT analysis for [company].

Company Overview:
- Industry: [industry]
- Founded: [year]
- Size: [employees, revenue]
- Market position: [leader/challenger/niche]

Key Competitors:
- [Competitor 1]: [brief description]
- [Competitor 2]: [brief description]

Recent Developments:
- [Development 1]
- [Development 2]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a SWOT analysis for a D2C skincare startup.

Company Overview:
- Industry: Beauty & Personal Care
- Founded: 2022
- Size: 25 employees, $3M ARR
- Market position: Challenger in clean beauty segment

Key Competitors:
- The Ordinary: Budget-friendly, science-focused
- Drunk Elephant: Premium clean beauty
- Glossier: Community-driven, minimalist

Recent Developments:
- Just launched in Target (500 stores)
- TikTok viral moment drove 10x traffic
- Raised Series A ($8M)

Theme: Cupertino
Primary color: #E91E8C
```

---

### PESTEL Analysis

**Basic PESTEL:**
```
Create a PESTEL analysis for [company/industry].

Industry: [industry]
Geography: [markets you operate in]
Time horizon: [next 1-3 years]
```

**Detailed PESTEL:**
```
Create a comprehensive PESTEL analysis for [company].

Company: [name]
Industry: [industry]
Key Markets: [countries/regions]

Focus Areas:
- Political: [specific concerns, e.g., regulation changes]
- Economic: [specific concerns, e.g., recession risk]
- Social: [specific trends to analyze]
- Technological: [specific technologies]
- Environmental: [specific concerns]
- Legal: [specific regulations]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a PESTEL analysis for an electric vehicle startup.

Company: VoltDrive
Industry: Electric Vehicles / Automotive
Key Markets: USA, EU, China

Focus Areas:
- Political: EV subsidies, infrastructure investment bills
- Economic: Interest rates affecting car loans, battery material costs
- Social: Climate consciousness, EV adoption rates by demographic
- Technological: Battery technology, autonomous driving, charging speed
- Environmental: Carbon regulations, battery recycling requirements
- Legal: Safety standards, right-to-repair laws, data privacy (connected cars)

Theme: Modern Minimal
Primary color: #16A34A
```

---

### Porter's Five Forces

```
Create a Porter's Five Forces analysis for [industry/company].

Industry: [industry]
Company position: [market leader/challenger/new entrant]

Context:
- [Any specific factors to consider]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a Porter's Five Forces analysis for the streaming video industry.

Industry: Video Streaming / OTT
Company position: New entrant (launching streaming service)

Context:
- Considering launching a niche streaming service for documentary content
- Would compete with Netflix, Disney+, Amazon Prime, HBO Max
- Have existing content library from documentary production company

Theme: Brutalist
```

---

### Competitive Analysis

**Basic Competitive Analysis:**
```
Create a competitive analysis for [product/company].

Our product: [name and brief description]

Competitors:
- [Competitor 1]
- [Competitor 2]
- [Competitor 3]

Compare on:
- Features
- Pricing
- Target market
- Strengths/Weaknesses
```

**Detailed Competitive Analysis:**
```
Create a comprehensive competitive analysis for [product].

Our Product:
- Name: [name]
- Category: [category]
- Price point: [price]
- Target market: [description]

Competitors to analyze:
1. [Competitor 1]: [URL or description]
2. [Competitor 2]: [URL or description]
3. [Competitor 3]: [URL or description]

Comparison dimensions:
- Core features
- Pricing & packaging
- Target audience
- Market positioning
- Strengths & weaknesses
- Market share (if known)
- Recent moves/announcements

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a competitive analysis for our project management tool.

Our Product:
- Name: FlowBoard
- Category: Project Management / Work OS
- Price point: $12/user/month
- Target market: SMB teams (10-100 people)

Competitors:
1. Asana: Enterprise-focused, complex features
2. Monday.com: Visual, marketing-heavy
3. Linear: Developer-focused, fast
4. Notion: Flexible but less structured

Comparison dimensions:
- Task management features
- Collaboration tools
- Integrations
- Mobile experience
- Pricing tiers
- Onboarding experience

Theme: Modern Minimal
Primary color: #6366F1
```

---

### Business Model Canvas

**Business Model Canvas:**
```
Create a Business Model Canvas for [company/product].

Brief description: [What the company does]
Stage: [Idea/Startup/Growth/Mature]
Industry: [industry]
```

**Lean Canvas:**
```
Create a Lean Canvas for [startup/product idea].

Problem: [Top 3 problems you're solving]
Solution: [Your proposed solution]
Target customers: [Who you're building for]
Unique value proposition: [Why you're different]
```

**Value Proposition Canvas:**
```
Create a Value Proposition Canvas for [product].

Customer Segment: [Who is the customer]

Customer Jobs:
- [What they're trying to accomplish]

Customer Pains:
- [What frustrates them]

Customer Gains:
- [What they want to achieve]
```

**Example - Business Model Canvas:**
```
Create a Business Model Canvas for a B2B SaaS analytics platform.

Brief description: Self-serve product analytics for mobile apps, like Mixpanel but simpler and cheaper
Stage: Startup (seed stage)
Industry: Analytics / Developer Tools

Key details:
- Freemium model with usage-based pricing
- Self-serve onboarding, no sales team yet
- Target: Indie developers and small startups
- Integrates with major mobile platforms

Theme: Material 3
Primary color: #7C3AED
```

**Example - Lean Canvas:**
```
Create a Lean Canvas for a food delivery app for healthy meals.

Problem:
1. Existing delivery apps have mostly unhealthy fast food options
2. Meal prep is time-consuming for health-conscious professionals
3. Calorie/macro information is unreliable on delivery apps

Solution:
- Curated marketplace of healthy restaurants only
- Verified nutritional information for every dish
- Meal planning features with dietary goal tracking

Target customers:
- Health-conscious urban professionals, 25-45
- Fitness enthusiasts tracking macros
- People with dietary restrictions

Unique value proposition:
"The only delivery app where everything is good for you"

Theme: Cupertino
Primary color: #34C759
```

---

## User Research

### User Personas

**Single Persona:**
```
Create a user persona for [product/service].

User segment: [Description of the user type]

Include:
- Demographics
- Goals & motivations
- Pain points & frustrations
- Behaviors & habits
- Tech savviness
- A day in their life
- Quote that captures them
```

**Multiple Personas:**
```
Create user personas for [product].

Persona 1: [Name/Type]
- [Brief description]

Persona 2: [Name/Type]
- [Brief description]

Persona 3: [Name/Type]
- [Brief description]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create three user personas for a personal finance app.

Persona 1: "The Recent Grad"
- Just started first job, has student loans
- Wants to build good financial habits early
- Overwhelmed by financial jargon

Persona 2: "The Family Planner"
- Dual income household, 2 kids
- Saving for house down payment and college
- Needs to track spending across multiple accounts

Persona 3: "The Pre-Retiree"
- 10 years from retirement
- Wants to maximize savings catch-up
- Concerned about market volatility

Theme: Modern Minimal
Primary color: #059669
```

---

### Customer Journey Map

**Basic Journey Map:**
```
Create a customer journey map for [product/service].

Journey: [What journey to map, e.g., "First purchase", "Onboarding"]

Stages:
1. [Stage 1]: [Brief description]
2. [Stage 2]: [Brief description]
3. [Stage 3]: [Brief description]

Include: Actions, thoughts, emotions, pain points, opportunities
```

**Detailed Journey Map:**
```
Create a comprehensive customer journey map for [product].

Persona: [Which persona is taking this journey]
Journey: [Specific journey]
Timeframe: [How long does this journey take]

Stages:
1. [Stage]: [Description]
   - Touchpoints: [Where they interact with us]
2. [Stage]: [Description]
   - Touchpoints: [Where they interact with us]

Current pain points to highlight:
- [Pain point 1]
- [Pain point 2]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a customer journey map for e-commerce first purchase.

Persona: First-time buyer, found us through Instagram ad
Journey: Discovery to First Purchase
Timeframe: 1-7 days typically

Stages:
1. Discovery: See Instagram ad, click through
   - Touchpoints: Instagram, landing page
2. Exploration: Browse products, read reviews
   - Touchpoints: Website, product pages
3. Consideration: Compare with competitors, check return policy
   - Touchpoints: FAQ, reviews, competitor sites
4. Decision: Add to cart, enter payment
   - Touchpoints: Cart, checkout
5. Post-Purchase: Order confirmation, shipping updates, delivery
   - Touchpoints: Email, SMS, package

Pain points to highlight:
- Shipping cost surprise at checkout
- Unclear size guide
- Slow mobile site

Theme: Cupertino
Primary color: #FF6B6B
```

---

### Jobs to Be Done (JTBD)

**Basic JTBD:**
```
Create a Jobs to be Done analysis for [product].

Main job: When [situation], I want to [motivation], so I can [outcome].

Include:
- Functional jobs
- Emotional jobs
- Social jobs
- Related jobs
```

**Example:**
```
Create a Jobs to be Done analysis for a meal kit delivery service.

Main job: When I get home tired after work, I want to make a healthy dinner quickly, so I can eat well without the mental load of meal planning.

Context:
- Target user: Busy professional, cooking skill level: intermediate
- Current alternatives: Takeout, frozen meals, grocery delivery

Theme: Material 3
Primary color: #F97316
```

---

### Empathy Map

```
Create an empathy map for [persona/user segment].

Context: [What situation/task are they in]

Focus on:
- Says: [Quotes, statements]
- Thinks: [Beliefs, concerns]
- Does: [Actions, behaviors]
- Feels: [Emotions]
- Pains: [Frustrations, obstacles]
- Gains: [Wants, needs, success measures]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create an empathy map for a first-time homebuyer using a mortgage app.

Context: Applying for their first mortgage, feeling overwhelmed by the process

Says:
- "I don't understand half these terms"
- "How much can I actually afford?"
- "My parents just went to a bank, why is this so complicated?"

Thinks:
- "Am I getting ripped off on rates?"
- "What if I get rejected?"
- "This is the biggest financial decision of my life"

Theme: Cupertino
Primary color: #0EA5E9
```

---

## Design

### Wireframes

**Mobile App Wireframes:**
```
Create mobile wireframes for [app/feature].

Screens:
1. [Screen name]: [Description, key elements]
2. [Screen name]: [Description, key elements]
3. [Screen name]: [Description, key elements]

Platform: iOS / Android / Both
Include: Navigation, key interactions, annotations

Theme: [brutalist/material/cupertino/minimal]
```

**Web App Wireframes:**
```
Create web wireframes for [application/feature].

Pages:
1. [Page name]: [Description, key sections]
2. [Page name]: [Description, key sections]

Include: Header, navigation, key components, responsive notes

Theme: [brutalist/material/cupertino/minimal]
```

**Example - Mobile:**
```
Create mobile wireframes for a fitness app onboarding flow.

Screens:
1. Welcome: App logo, value proposition, "Get Started" button
2. Goal Selection: Cards for goals (Lose weight, Build muscle, Stay active, etc.)
3. Experience Level: Beginner/Intermediate/Advanced selection
4. Availability: Days per week selector, preferred workout duration
5. Personal Info: Age, height, weight (optional)
6. Plan Preview: Show generated workout plan, "Start Now" CTA

Platform: iOS
Include: Progress indicator, skip options, back navigation

Theme: Cupertino
Primary color: #FF2D55
```

**Example - Web Dashboard:**
```
Create wireframes for an analytics dashboard.

Pages:
1. Dashboard Home:
   - KPI cards at top (4 key metrics)
   - Main chart (line graph, time series)
   - Secondary charts (2 columns)
   - Recent activity feed

2. Reports Page:
   - Filter sidebar
   - Data table with sorting/pagination
   - Export buttons

3. Settings:
   - Tabbed interface
   - Form sections for different settings

Theme: Modern Minimal
Primary color: #6366F1
```

---

## Technical Documentation

### Technical Spec

**Feature Technical Spec:**
```
Create a technical spec for [feature].

Overview:
- Problem: [What problem this solves]
- Solution: [High-level approach]
- Scope: [What's included/excluded]

Requirements:
- [Requirement 1]
- [Requirement 2]

Include: Architecture, API design, data model, security considerations

Theme: [brutalist/material/cupertino/minimal]
```

**System Design Spec:**
```
Create a technical spec for [system/service].

System: [Name and purpose]
Scale: [Expected load, users, data volume]

Requirements:
- Functional: [List]
- Non-functional: [Latency, availability, etc.]

Constraints:
- [Technical constraints]
- [Business constraints]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a technical spec for a real-time notification system.

Overview:
- Problem: Users miss important updates, only email notifications exist
- Solution: Multi-channel notifications (push, in-app, email)
- Scope: Web push, mobile push, in-app; excludes SMS for v1

Requirements:
- Delivery latency: <500ms for 95th percentile
- Support 1M+ connected users
- User preferences (channel, frequency, do-not-disturb)
- Delivery tracking and analytics

Constraints:
- Must integrate with existing user service
- Budget: <$500/month at current scale
- Team: 2 engineers, 6-week timeline

Theme: Brutalist
```

---

### API Documentation

**REST API Docs:**
```
Create API documentation for [API name].

Base URL: [URL]
Authentication: [Method]

Endpoints:
- [METHOD] [path]: [Description]
- [METHOD] [path]: [Description]

Include: Request/response examples, error codes, rate limits

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create API documentation for a user management API.

Base URL: https://api.example.com/v1
Authentication: Bearer token (JWT)

Endpoints:
- POST /auth/register: Create new user account
- POST /auth/login: Authenticate and get tokens
- POST /auth/refresh: Refresh access token
- GET /users/me: Get current user profile
- PATCH /users/me: Update current user profile
- DELETE /users/me: Delete account
- GET /users/:id: Get user by ID (admin only)
- GET /users: List users with pagination (admin only)

Include: Full request/response schemas, error codes, rate limits

Theme: Modern Minimal
Primary color: #18181B
```

---

### Database Schema

**New Database Design:**
```
Create database schema documentation for [project].

Database: [PostgreSQL/MySQL/MongoDB/etc.]
Platform: [Self-hosted/AWS RDS/Supabase/etc.]

Entities:
- [Entity 1]: [Description]
- [Entity 2]: [Description]

Include: ERD diagram, table definitions, indexes, relationships

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create database schema documentation for a multi-tenant SaaS CRM.

Database: PostgreSQL 15
Platform: Supabase

Entities:
- organizations: Tenant accounts with billing info
- users: Team members with roles
- contacts: Customer contacts
- deals: Sales opportunities with stages
- activities: Emails, calls, meetings linked to contacts/deals
- custom_fields: User-defined fields per tenant

Requirements:
- Row-level security for multi-tenancy
- Soft deletes for compliance
- Audit logging for sensitive operations

Include: ERD, indexes, RLS policies, migration strategy

Theme: Brutalist
```

---

### Infrastructure Documentation

```
Create infrastructure documentation for [project].

Stack:
- [Service]: [Purpose]
- [Service]: [Purpose]

Requirements:
- Availability: [Target uptime]
- Scale: [Expected users/traffic]
- Budget: [Monthly target]

Include: Architecture diagram, service configs, costs, monitoring

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create infrastructure documentation for a real-time collaboration app.

Stack:
- Vercel: Next.js frontend hosting
- Supabase: PostgreSQL database, auth, real-time subscriptions
- Cloudflare: CDN, DDoS protection, edge functions
- Upstash: Redis for presence and ephemeral data
- Resend: Transactional email

Requirements:
- Availability: 99.9% uptime
- Scale: 50K DAU, 5K concurrent users
- Budget: <$800/month initially

Include: Architecture diagram, scaling strategy, disaster recovery, cost breakdown

Theme: Modern Minimal
```

---

### Analytics Framework

```
Create analytics documentation for [product].

Analytics platform: [Mixpanel/Amplitude/PostHog/etc.]

Key metrics:
- [Metric]: [Definition]
- [Metric]: [Definition]

Key events:
- [Event]: [When triggered]
- [Event]: [When triggered]

Include: Event taxonomy, user properties, funnels, dashboards

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create analytics documentation for a subscription meditation app.

Analytics platform: Amplitude

Key metrics:
- MAU: Monthly active users
- Meditation minutes: Total minutes meditated
- Subscription conversion: Free trial to paid
- D1/D7/D30 retention: By cohort

Key events:
- session_started: User opens app
- meditation_started: User starts a meditation
- meditation_completed: User finishes (with duration)
- subscription_started: User converts to paid
- subscription_cancelled: User cancels

Funnels:
- Onboarding completion
- Free trial to paid conversion
- First meditation to habit formation

Theme: Cupertino
Primary color: #8B5CF6
```

---

## User-Facing Documentation

### User Guide

```
Create a user guide for [product/feature].

Audience: [Who will read this]
Skill level: [Beginner/Intermediate/Advanced]

Sections:
- [Section 1]
- [Section 2]
- [Section 3]

Tone: [Friendly/Professional/Technical]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create a user guide for our project management app.

Audience: New users, non-technical team leads
Skill level: Beginner

Sections:
- Getting Started (account setup, first project)
- Managing Tasks (create, assign, due dates, priorities)
- Collaboration (comments, @mentions, file attachments)
- Views (Kanban, List, Calendar, Timeline)
- Integrations (Slack, Google Calendar, GitHub)
- Tips & Shortcuts

Tone: Friendly, encouraging, with lots of examples

Theme: Material 3
Primary color: #2563EB
```

---

### Release Notes

```
Create release notes for [product] version [X.X.X].

Release date: [Date]

Changes:
- New: [Features]
- Improved: [Enhancements]
- Fixed: [Bug fixes]
- Breaking: [Breaking changes, if any]

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create release notes for TaskFlow version 3.2.0.

Release date: January 15, 2025

Changes:
- New:
  - Dark mode (finally!)
  - Keyboard shortcuts for power users
  - Recurring tasks with custom schedules
  - Bulk edit mode for tasks

- Improved:
  - Search is 3x faster
  - Mobile app performance improvements
  - Better onboarding flow for new users

- Fixed:
  - Calendar sync missing some events
  - Push notifications delayed on Android
  - Export to CSV missing custom fields

- Breaking:
  - Dropped support for iOS 14 (now requires iOS 15+)
  - API v1 deprecated (use v2)

Migration guide for API changes: [Include section]

Theme: Modern Minimal
```

---

### Onboarding Documentation

```
Create onboarding documentation for [audience].

Audience: [New engineers/New employees/Contractors/etc.]
Team: [Which team they're joining]

Include:
- Day 1 checklist
- Week 1 goals
- Key tools and access
- Important contacts
- Resources and documentation links

Theme: [brutalist/material/cupertino/minimal]
```

**Example:**
```
Create onboarding documentation for new frontend engineers.

Audience: New frontend engineers
Team: Product Engineering

Include:
- Day 1: Accounts setup (GitHub, Slack, Figma, Jira), meet the team
- Week 1: Dev environment setup, first PR, architecture overview
- Week 2-4: Buddy system, first feature assignment

Tools:
- Code: GitHub, VS Code, Node 20, pnpm
- Design: Figma
- Communication: Slack, Notion
- Project management: Linear

Key contacts:
- Engineering Manager: [Name]
- Tech Lead: [Name]
- Onboarding Buddy: [Name]
- HR Contact: [Name]

Theme: Material 3
Primary color: #7C3AED
```

---

## Composite Workflows

These prompts combine multiple skills for comprehensive documentation.

### New Product Launch Package

```
Create a complete product launch documentation package for [product].

Include:
1. PRD - Product requirements
2. User Personas - 2-3 key personas
3. Wireframes - Key screens (5-7 screens)
4. Technical Spec - Architecture overview
5. Launch Playbook - Go-to-market plan

Product: [Description]
Target launch: [Date]
Target users: [Description]

Theme: [consistent across all docs]
Primary color: [hex]
```

**Example:**
```
Create a complete product launch documentation package for a habit tracking app.

Include:
1. PRD - Core habit tracking features
2. User Personas - Casual user, power user, accountability seeker
3. Wireframes - Onboarding, home, habit detail, stats, settings
4. Technical Spec - Mobile architecture, sync strategy
5. Launch Playbook - Beta to public launch plan

Product: "Streaks" - Simple habit tracking focused on building streaks
Target launch: Q2 2025
Target users: Young professionals wanting to build better daily habits

Theme: Cupertino
Primary color: #FF9500
```

---

### Startup Pitch Package

```
Create a startup documentation package for [startup/idea].

Include:
1. Lean Canvas - Business model overview
2. Competitive Analysis - Market landscape
3. User Personas - Target customers
4. PRD - MVP features
5. Roadmap - Now/Next/Later for first year

Startup: [Name and description]
Stage: [Idea/Pre-seed/Seed]
Industry: [Industry]

Theme: [consistent across all]
```

**Example:**
```
Create a startup documentation package for a sustainable fashion marketplace.

Include:
1. Lean Canvas - Two-sided marketplace model
2. Competitive Analysis - vs ThredUp, Poshmark, Depop
3. User Personas - Eco-conscious seller, value-seeking buyer
4. PRD - MVP marketplace features
5. Roadmap - Launch to Series A milestones

Startup: "ReWear" - Curated secondhand fashion marketplace for premium brands
Stage: Pre-seed
Industry: E-commerce / Fashion / Sustainability

Theme: Modern Minimal
Primary color: #059669
```

---

### Enterprise Feature Package

```
Create enterprise feature documentation for [feature].

Include:
1. PRD - Detailed requirements
2. Technical Spec - Architecture and security
3. Database Schema - Data model changes
4. API Documentation - New endpoints
5. User Guide - Admin configuration guide

Feature: [Description]
Target customers: [Enterprise segment]
Compliance requirements: [SOC2/GDPR/HIPAA/etc.]

Theme: [consistent across all]
```

---

### Strategic Planning Package

```
Create a strategic planning documentation package for [company/product].

Include:
1. SWOT Analysis - Internal and external factors
2. PESTEL Analysis - Macro environment
3. Competitive Analysis - Market positioning
4. Business Model Canvas - Current state
5. Roadmap - Strategic initiatives

Company: [Name]
Industry: [Industry]
Planning horizon: [1 year / 3 years]

Theme: [consistent across all]
```

---

### User Research Package

```
Create a user research documentation package for [product].

Include:
1. User Personas - 3 key segments
2. Customer Journey Map - Primary user flow
3. Empathy Maps - For each persona
4. JTBD Analysis - Core jobs to be done

Research basis: [Interviews/Surveys/Analytics/Assumptions]
Product: [Description]
Target users: [Description]

Theme: [consistent across all]
```

---

### API Product Package

```
Create an API product documentation package for [API].

Include:
1. PRD - API product requirements
2. API Documentation - Full endpoint reference
3. Technical Spec - Architecture, rate limiting, auth
4. User Guide - Getting started guide for developers

API: [Name and purpose]
Target developers: [Who will use this API]
Pricing model: [Free/Freemium/Paid]

Theme: [consistent across all]
```

---

## Tips & Best Practices

### General Tips

1. **Be specific** — More context = better output
2. **Use examples** — Include sample data when relevant
3. **Specify audience** — Who will read this document?
4. **Choose the right theme** — Match your brand or use case
5. **Iterate** — Ask for specific sections to be revised

### Theme Recommendations

| Use Case | Recommended Theme |
|----------|-------------------|
| Developer/technical docs | Brutalist |
| SaaS products | Material 3 |
| iOS/macOS apps | Cupertino |
| Startups, modern brands | Modern Minimal |
| Enterprise | Modern Minimal or Material 3 |

### Prompt Structure

Best prompts follow this structure:

```
[What to create] for [context].

[Key details organized clearly]

[Specific requirements or constraints]

Theme: [choice]
Primary color: [if using custom]
```

### Plan Mode for Complex Docs

For complex documents, use plan mode:

```
Enter plan mode. I need to create [document type] for [project].

First, establish my design system:
- Theme: [preference]
- Colors: Primary [hex], Accent [hex]
- Mode: [light/dark]

Then create the document with these requirements:
[Your specific requirements]
```

This ensures consistency even if context compacts during long sessions.

---

## Output

All documents are saved as self-contained HTML files:

```
./outputs/[document-name].html
```

- Open directly in any browser
- No build step required
- Print-ready
- Easy to share
