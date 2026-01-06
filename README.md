# MAflow

> **Your AI-Powered Development Team** — From Vision to Production

MAflow is an intelligent skill-based system that simulates a complete software development team, guiding projects from initial concept through development and quality assurance. Built on 17+ years of real-world software engineering experience, MAflow brings proven industry workflows to AI-assisted development.

---

## About the Creator

**Mohammad Asif** — Senior Software Engineer with 17+ years of experience designing, developing, and maintaining software systems across diverse technologies and domains. This project distills years of industry knowledge into AI-powered skills that help developers build production-ready software faster and smarter.

---

## Vision

The future of software development is AI-assisted. MAflow bridges the gap between traditional software engineering practices and modern AI capabilities, creating a system where:

- **Experience meets AI** — Proven workflows encoded into intelligent skills
- **Teams are simulated** — BA, Architect, PM, Developer, QA working together
- **Quality is built-in** — Production-ready outputs from day one
- **Efficiency is maximized** — Minimal input, maximum output

---

## How It Works

MAflow simulates the workflow of a professional software development organization:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                              MAflow Workflow                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│   [Client/Developer]                                                        │
│         │                                                                   │
│         ▼                                                                   │
│   ┌─────────────┐     ┌──────────────────┐                                  │
│   │  Business   │────▶│    Solution      │                                  │
│   │  Analyst    │◀────│    Architect     │                                  │
│   └─────────────┘     └──────────────────┘                                  │
│         │                     │                                             │
│         ▼                     ▼                                             │
│   ┌─────────────────────────────────────┐                                   │
│   │         CLAUDE.md (Source of Truth) │                                   │
│   └─────────────────────────────────────┘                                   │
│                       │                                                     │
│                       ▼                                                     │
│               ┌───────────────┐                                             │
│               │    Project    │                                             │
│               │    Manager    │                                             │
│               └───────────────┘                                             │
│                       │                                                     │
│         ┌─────────────┼─────────────┐                                       │
│         ▼             ▼             ▼                                       │
│   ┌──────────┐  ┌──────────┐  ┌──────────┐                                  │
│   │ TASKS-   │  │ TASKS-   │  │ TASKS-   │                                  │
│   │ backend  │  │ frontend │  │ mobile   │                                  │
│   │   .md    │  │   .md    │  │   .md    │                                  │
│   └──────────┘  └──────────┘  └──────────┘                                  │
│         │             │             │                                       │
│         ▼             ▼             ▼                                       │
│   ┌─────────────────────────────────────┐                                   │
│   │         Software Engineer           │                                   │
│   │      (Development & Coding)         │                                   │
│   └─────────────────────────────────────┘                                   │
│                       │                                                     │
│                       ▼                                                     │
│   ┌─────────────────────────────────────┐                                   │
│   │        Quality Assurance            │                                   │
│   │    (Testing & Issue Tracking)       │                                   │
│   └─────────────────────────────────────┘                                   │
│                       │                                                     │
│                       ▼                                                     │
│               [Production Ready]                                            │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Skills

MAflow consists of five specialized skills, each representing a role in a development team:

### 1. Business Analyst (`business-analyst`)

**Purpose:** Gather requirements and create the project's source of truth.

**Input:** Initial project idea or description from client/developer

**Process:**
1. **Project Vision** — Collects name, description, problem statement
2. **Features** — Suggests features based on project type, allows selection
3. **Technology Stack** — Recommends technologies, confirms preferences
4. **Third-party Integrations** — Identifies required SDKs/libraries

**Output:** `CLAUDE.md` — The comprehensive project specification

**Key Features:**
- Minimal questions, maximum suggestions
- Smart inference from project description
- Multi-select options with "All of the above" convenience
- Supports multi-platform projects (backend, web, mobile, admin)

---

### 2. Solution Architect (`solution-architect`)

**Purpose:** Validate technical feasibility and define system architecture.

**Input:** Requirements from Business Analyst, `CLAUDE.md`

**Process:**
1. **Review Requirements** — Analyze feasibility of proposed features
2. **Identify Gray Areas** — Flag unclear or risky requirements
3. **Platform Breakdown** — Define which platforms are needed
4. **Architecture Decisions** — Document key technical decisions
5. **Risk Assessment** — Identify technical risks and mitigations

**Output:** Updated `CLAUDE.md` with architecture decisions and platform breakdown

**Collaboration:** Works with BA to clarify requirements with client when needed

---

### 3. Project Manager (`project-manager`)

**Purpose:** Break down the project into actionable, trackable tasks.

**Input:** Approved `CLAUDE.md` from BA and Architect

**Process:**
1. **Platform Identification** — Determine all platforms to build
2. **Module Breakdown** — Divide each platform into logical modules
3. **Task Creation** — Create detailed tasks with acceptance criteria
4. **Dependency Mapping** — Identify cross-platform dependencies
5. **Phase Planning** — Organize tasks into development phases

**Output:** 
- `TASKS-{platform}.md` — One task file per platform
- Tasks organized by module/phase
- Clear dependency references between tasks

**Task Structure:**
```markdown
## Module: Authentication

### TASK-001: Implement User Registration API
- **Priority:** High
- **Size:** M (2-4 hours)
- **Dependencies:** None
- **Acceptance Criteria:**
  - [ ] POST /api/auth/register endpoint
  - [ ] Email validation
  - [ ] Password hashing
  - [ ] Returns JWT token
```

---

### 4. Software Engineer (`software-engineer`)

**Purpose:** Implement tasks and write production-quality code.

**Input:** Task assignments from `TASKS-{platform}.md`

**Process:**
1. **Task Selection** — Pick task from assigned platform
2. **Dependency Check** — Verify dependent tasks are completed
3. **Implementation** — Write code following project guidelines
4. **Self-Review** — Ensure code meets acceptance criteria
5. **Task Completion** — Mark task as complete, update task file

**Output:** 
- Working code implementation
- Updated task status in `TASKS-{platform}.md`

**Guidelines:**
- Follow coding standards defined in `CLAUDE.md`
- Check dependencies before starting work
- Mark tasks complete only when all criteria met

---

### 5. Quality Assurance (`quality-assurance`)

**Purpose:** Test completed modules and track issues.

**Input:** 
- Test instructions from Project Manager
- Completed modules from Software Engineer

**Process:**
1. **Receive Test Plan** — PM provides testing instructions per module
2. **Execute Tests** — Run through test scenarios
3. **Log Issues** — Document any bugs or failures found
4. **Track Resolution** — Monitor issue fixes by developers
5. **Verify Fixes** — Confirm issues are resolved

**Output:** `{module-name}.md` — Issue tracking file per module

**Issue Structure:**
```markdown
## ISSUE-001: Login fails with valid credentials

- **Status:** Open | Resolved | Verified | Reopened
- **Severity:** Critical | High | Medium | Low
- **Module:** Authentication
- **Steps to Reproduce:**
  1. Navigate to /login
  2. Enter valid email and password
  3. Click "Sign In"
- **Expected:** User logged in, redirected to dashboard
- **Actual:** Error message "Invalid credentials"
- **Screenshot:** [if applicable]

### Resolution (by Developer):
Fixed null check in auth middleware. Root cause was...

### Verification (by QA):
✅ FIXED - Verified on 2024-01-15
```

---

## Document Structure

MAflow generates and maintains these key documents:

```
project/
├── CLAUDE.md                 # Source of truth (by BA + Architect)
├── TASKS-backend.md          # Backend tasks (by PM)
├── TASKS-frontend.md         # Frontend tasks (by PM)
├── TASKS-mobile.md           # Mobile tasks (by PM)
├── TASKS-admin.md            # Admin dashboard tasks (by PM)
└── qa/
    ├── authentication.md     # Auth module issues (by QA)
    ├── booking.md            # Booking module issues (by QA)
    └── payments.md           # Payment module issues (by QA)
```

---

## Workflow Example: Ride-Hailing App

**Step 1: Business Analyst**
```
Developer: I want to build a ride-hailing app like Uber

BA: Based on "ride-hailing app", here are typical Rider features:
    1. Registration/Login
    2. Book a ride
    3. Live tracking
    ...
    7. All of the above
    8. Other

Developer: 7

BA: Here are typical Driver features:
    ...

[Generates CLAUDE.md with all requirements]
```

**Step 2: Solution Architect**
```
Architect: Reviewing CLAUDE.md...

Platforms identified:
- Backend API (Node.js + Express)
- Rider App (React Native)
- Driver App (React Native)
- Admin Dashboard (React)

Architecture decisions documented...
Risk assessment completed...

[Updates CLAUDE.md with technical details]
```

**Step 3: Project Manager**
```
PM: Breaking down into tasks...

[Generates]
- TASKS-backend.md (47 tasks)
- TASKS-rider-app.md (32 tasks)
- TASKS-driver-app.md (28 tasks)
- TASKS-admin.md (24 tasks)

Dependencies mapped:
- TASK-RIDER-015 depends on TASK-BACKEND-008
- TASK-DRIVER-012 depends on TASK-BACKEND-008
```

**Step 4: Software Engineer**
```
Dev: Starting TASK-BACKEND-001: Project Setup

[Implements task]
[Marks complete in TASKS-backend.md]

Dev: Starting TASK-BACKEND-002: Database Schema
...
```

**Step 5: Quality Assurance**
```
QA: Testing Authentication Module

[Creates authentication.md]

ISSUE-001: OTP not received on some carriers
- Status: Open
- Severity: High
...

[Developer fixes, marks resolved]

QA: ✅ FIXED - Verified
```

---

## Installation & Usage

### Prerequisites
- Claude AI with skills support
- Access to Claude's computer use capabilities

### Installing Skills

1. Download the `.skill` files from this repository
2. Upload to your Claude skills directory
3. Skills will be available in your Claude conversations

### Using MAflow

**Start a new project:**
```
You: I want to start a new project

Claude: [Activates business-analyst skill]
What's the name of your project?
```

**Generate tasks:**
```
You: Create tasks for this project

Claude: [Activates project-manager skill]
[Reads CLAUDE.md, generates TASKS-*.md files]
```

**Develop a feature:**
```
You: Start working on the authentication module

Claude: [Activates software-engineer skill]
[Checks dependencies, implements tasks]
```

---

## Design Principles

### 1. Minimal Input, Maximum Output
Skills infer as much as possible from context, reducing developer burden.

### 2. Opinionated but Flexible
Provides smart defaults while always allowing customization via "Other" options.

### 3. Document-Driven
All decisions and progress tracked in markdown files — the source of truth.

### 4. Dependency-Aware
Tasks explicitly reference dependencies, preventing blocked work.

### 5. Quality Built-In
QA is integrated into the workflow, not an afterthought.

---

## Roadmap

- [x] Business Analyst skill
- [ ] Solution Architect skill
- [ ] Project Manager skill
- [ ] Software Engineer skill
- [ ] Quality Assurance skill
- [ ] Slash commands for quick actions
- [ ] Sub-agent orchestration
- [ ] Integration with external tools (GitHub, Jira)

---

## Contributing

This project is in active development. Contributions, suggestions, and feedback are welcome.

---

## License

MIT License — See [LICENSE](LICENSE) for details.

---

## Contact

**Mohammad Asif**  
Senior Software Engineer | 17+ Years Experience  
Building the future of AI-assisted software development

---

<p align="center">
  <strong>MAflow</strong> — Your AI Development Team<br>
  <em>From Vision to Production</em>
</p>