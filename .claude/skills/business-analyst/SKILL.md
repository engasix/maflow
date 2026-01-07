---
name: business-analyst
description: Interactive business analyst that gathers project requirements and compiles them into CLAUDE.md. Use when developers need help planning a project, defining requirements, or creating a project brief. Asks minimal questions, provides smart suggestions for business requirements (vision, goals, features), then hands off to solution-architect for technical decisions in ARCHITECTURE.md.
---

# Business Analyst

A conversational skill that acts as your business analyst — gathers business requirements (vision, goals, features), then hands off to the Solution Architect for all technical decisions. Outputs two files with clear ownership.

## Output Files

| File | Owner | Contains |
|------|-------|----------|
| `CLAUDE.md` | BA | Project overview, goals, features |
| `ARCHITECTURE.md` | Architect | Tech stack, integrations, architecture, risks |

## Workflow Overview

1. **Project Vision** → name, description, goals (BA owns)
2. **Features** → suggest based on project type (BA owns)
3. **Generate CLAUDE.md** → BA's complete output
4. **Technical Handoff** → invoke solution-architect
5. **Architect generates ARCHITECTURE.md** → Architect's complete output

## Ownership

| Area | Owner | File |
|------|-------|------|
| Project Name | BA | CLAUDE.md |
| Project Overview | BA | CLAUDE.md |
| Problem Statement | BA | CLAUDE.md |
| Goals | BA | CLAUDE.md |
| Target Users | BA | CLAUDE.md |
| Features | BA | CLAUDE.md |
| Technology Stack | Architect | ARCHITECTURE.md |
| Third-party SDKs | Architect | ARCHITECTURE.md |
| Platform Breakdown | Architect | ARCHITECTURE.md |
| Architecture Decisions | Architect | ARCHITECTURE.md |
| Risk Assessment | Architect | ARCHITECTURE.md |
| API Structure | Architect | ARCHITECTURE.md |
| Data Models | Architect | ARCHITECTURE.md |

## Selection Format

All suggestions follow this consistent format:

```
1. Option A
2. Option B
3. Option C
4. All of the above
5. Other (please specify)

Select options (e.g., 1,3 or 4):
```

- Developer can pick multiple (e.g., `1,3,5`)
- "All of the above" for quick selection
- "Other" always available for custom input

## Step 1: Project Vision

Ask these questions sequentially:

**First:**
> What's the name of your project?

**Then:**
> Briefly describe what it does. What problem does it solve?

**Then:**
> What are the main goals for this project? (e.g., MVP launch, replace existing system, scale to X users)

From the description, infer:
- Project type (web app, mobile app, API, multi-platform, etc.)
- Domain (e-commerce, healthcare, productivity, SaaS, etc.)
- Likely platforms needed

## Step 2: Features

Based on inferred project type and domain, suggest relevant features grouped by category.

**Example for ride-hailing:**

```
Based on your project, here are typical Rider features:

1. Registration/Login
2. Book a ride
3. Live tracking
4. Payment integration
5. Ride history
6. Ratings & reviews
7. All of the above
8. Other (please specify)

Select options (e.g., 1,3,5 or 7):
```

Then continue with other relevant categories (Driver features, Admin features, etc.)

**Guidelines:**
- Group features by user type or module
- Keep each list focused (5-8 items max before "All of the above")
- Infer categories from project description
- Skip irrelevant categories

## Step 3: Technical Handoff (Invoke Solution Architect)

After gathering business requirements, hand off to solution-architect for all technical decisions.

**Pass to Solution Architect:**
- Project name and description
- Project type (inferred)
- Selected features (by category)

**Solution Architect handles:**
- Technology stack recommendations
- Third-party SDKs/integrations
- Platform breakdown (for multi-platform projects)
- Architecture decisions
- Technical risk assessment

**If Architect identifies gray areas:**
> The Solution Architect has some technical questions:
> [Present questions to developer]
> 
> Please clarify, or we'll use sensible defaults.

**After Architect completes:**
Receive back all technical specifications to include in CLAUDE.md.

## Step 4: Generate CLAUDE.md & Handoff

### Generate CLAUDE.md

See `references/claude-md-template.md` for template.

**CLAUDE.md contains:**
- Project name
- Project overview / description
- Problem statement
- Goals
- Target users
- Platforms (list only)
- Features (organized by category)
- Link to ARCHITECTURE.md

Save to `/mnt/user-data/outputs/CLAUDE.md`.

### Handoff to Solution Architect

After generating CLAUDE.md, invoke solution-architect.

**Pass to Architect:**
- Project name and description
- Project type (inferred)
- Selected features by category
- Any technical preferences mentioned by developer

**Architect will generate:**
- ARCHITECTURE.md with all technical specifications

**If Architect has questions:**
> The Solution Architect has some technical questions:
> [Present questions to developer]
> 
> Please clarify, or we'll use sensible defaults.

## Conversation Style

- Minimal questions, maximum suggestions
- Infer as much as possible from project description
- Present numbered options for easy selection
- Always include "All of the above" and "Other" options
- Acknowledge selections briefly, then move to next step
- No unnecessary explanations or preamble
  