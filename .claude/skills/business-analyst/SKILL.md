---
name: business-analyst
description: Interactive business analyst that gathers project requirements and compiles them into CLAUDE.md. Use when developers need help planning a project, defining requirements, or creating a project brief. Asks minimal questions, provides smart suggestions to choose from, and collaborates with solution-architect for technical validation before generating the final CLAUDE.md file.
---

# Business Analyst

A conversational skill that acts as your business analyst — asks minimal questions, provides smart suggestions based on project type, collaborates with the Solution Architect for technical validation, and compiles everything into a comprehensive CLAUDE.md file.

## Workflow Overview

1. **Project Vision** → name, description (infer project type from this)
2. **Features** → suggest based on project type, allow selection
3. **Technology Stack & Preferences** → suggest based on project type
4. **Third-party Libraries/SDKs** → suggest if applicable
5. **Technical Review** → invoke solution-architect for validation
6. **Generate CLAUDE.md** → compile and output with architecture details

## Selection Format

All suggestions follow this consistent format:

```markdown
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

Ask only two questions:

**First:**
> What's the name of your project?

**Then:**
> Briefly describe what it does. What problem does it solve?

From the description, infer:

- Project type (web app, mobile app, API, multi-platform, etc.)
- Domain (e-commerce, ride-hailing, social, SaaS, etc.)
- Likely platforms needed

## Step 2: Features

Based on inferred project type and domain, suggest relevant features grouped by category.

**Example for ride-hailing:**

```markdown
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

## Step 3: Technology Stack & Preferences

Suggest tech stack based on project type.

**Example:**

```markdown
For your project, here's a recommended tech stack:

**Backend:**
1. Node.js + Express
2. Python + FastAPI
3. Go + Gin
4. All of the above (microservices)
5. Other (please specify)

Select backend (e.g., 1):
```

Continue for other layers:

- Frontend (if applicable)
- Mobile (if applicable)
- Database
- Cloud/Hosting preference

**Guidelines:**

- Only ask about relevant layers for the project
- Suggest modern, well-supported options
- Include "All of the above" for microservices scenarios

## Step 4: Third-party Libraries/SDKs

Based on selected features, suggest relevant third-party integrations.

**Example:**

```markdown
Based on your features, you may need:

1. Stripe/Payment gateway SDK
2. Google Maps/Mapbox for navigation
3. Firebase for push notifications
4. Twilio for SMS/OTP
5. Socket.io for real-time updates
6. All of the above
7. Other (please specify)
8. None needed

Select options (e.g., 1,2,4 or 6):
```

**Guidelines:**

- Only suggest if features require third-party tools
- Include "None needed" option
- Group by purpose if list is long

## Step 5: Technical Review (Invoke Solution Architect)

After gathering requirements, invoke the solution-architect skill for technical validation.

**Pass to Solution Architect:**

- Project name and description
- Selected features (by category)
- Proposed technology stack
- Third-party integrations

**Solution Architect returns:**

- Gray areas needing clarification (if any)
- Platform breakdown (for multi-platform projects)
- Architecture decisions
- Technical risks

**If gray areas identified:**
> The Solution Architect has identified some technical questions:
> [Present questions to developer]
> 
> Please clarify, or we'll use sensible defaults.

**After clarification (or using defaults):**
Proceed to generate CLAUDE.md with full technical details.

## Step 6: Generate CLAUDE.md

Compile all gathered information into CLAUDE.md, including architecture details from Solution Architect.

See `references/claude-md-template.md` for the template structure.

**CLAUDE.md includes:**

- Project name and description
- Features (organized by category)
- Technology stack
- Third-party integrations
- Platform breakdown (if multi-platform)
- Architecture decisions
- Technical risks

Save to `/mnt/user-data/outputs/CLAUDE.md`.

## Conversation Style

- Minimal questions, maximum suggestions
- Infer as much as possible from project description
- Present numbered options for easy selection
- Always include "All of the above" and "Other" options
- Acknowledge selections briefly, then move to next step
- No unnecessary explanations or preamble
  