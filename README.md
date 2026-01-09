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
- **Teams are simulated** — BA, Architect, PM, Developers, QA working together
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
│   ┌─────────────┐                                                           │
│   │  Business   │                                                           │
│   │  Analyst    │ ──────────────────────────────────────┐                   │
│   └─────────────┘                                       │                   │
│         │                                               │                   │
│         ▼                                               ▼                   │
│   ┌─────────────┐                              ┌──────────────────┐         │
│   │ CLAUDE.md   │                              │    Solution      │         │
│   │ (BA Output) │                              │    Architect     │         │
│   └─────────────┘                              └──────────────────┘         │
│                                                         │                   │
│                                                         ▼                   │
│                                                ┌──────────────────┐         │
│                                                │ ARCHITECTURE.md  │         │
│                                                │(Architect Output)│         │
│                                                └──────────────────┘         │
│                                                         │                   │
│         ┌───────────────────────────────────────────────┘                   │
│         ▼                                                                   │
│   ┌───────────────┐                                                         │
│   │    Project    │                                                         │
│   │    Manager    │                                                         │
│   └───────────────┘                                                         │
│         │                                                                   │
│         ├──────────────────────────────────────────────────┐                │
│         │                                                  │                │
│         ▼                                                  ▼                │
│   ┌─────────────┐                                  ┌─────────────┐          │
│   │   .claude/  │                                  │   tasks/    │          │
│   │   agents/   │                                  │             │          │
│   ├─────────────┤                                  ├─────────────┤          │
│   │ backend-    │                                  │ TASKS-      │          │
│   │ developer.md│                                  │ backend.md  │          │
│   │ frontend-   │                                  │ TASKS-      │          │
│   │ developer.md│                                  │ frontend.md │          │
│   │ qa.md       │                                  └─────────────┘          │
│   └─────────────┘                                                           │
│         │                                                  │                │
│         │              ┌───────────────────────────────────┘                │
│         ▼              ▼                                                    │
│   ┌─────────────────────────────────────┐                                   │
│   │      Platform Sub-Agents            │                                   │
│   │   (Execute tasks, write code)       │                                   │
│   └─────────────────────────────────────┘                                   │
│                       │                                                     │
│                       ▼                                                     │
│   ┌─────────────────────────────────────┐                                   │
│   │        QA Sub-Agent                 │                                   │
│   │  (Test & log issues in task files)  │                                   │
│   └─────────────────────────────────────┘                                   │
│                       │                                                     │
│                       ▼                                                     │
│               [Production Ready]                                            │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Skills vs Sub-Agents

MAflow uses two types of AI workers:

| Type | What It Is | Created By | Examples |
|------|------------|------------|----------|
| **Skill** | Reusable capability, part of MAflow system | MAflow (packaged as .skill) | business-analyst, solution-architect, project-manager |
| **Sub-Agent** | Project-specific worker, created per project | Project Manager | backend-developer, frontend-developer, qa |

---

## Folder Structure

```
/
├── .claude/
│   └── agents/                      # Sub-agents (created by PM)
│       ├── backend-developer.md
│       ├── frontend-developer.md
│       └── qa.md
│
├── CLAUDE.md                        # Project requirements (by BA)
├── ARCHITECTURE.md                  # Technical specs (by Architect)
│
├── tasks/                           # Task files (created by PM)
│   ├── TASKS-backend.md             # Tasks + Test Cases + Issues
│   └── TASKS-frontend.md
│
└── {project-name}/                  # Code only (by Sub-agents)
    ├── backend/
    └── frontend/
```

---

## Skills

MAflow consists of three core skills that work together:

### 1. Business Analyst (`business-analyst`)

**Purpose:** Gather requirements and create the project specification.

**Workflow:**
1. **Project Vision** — Collects name, description, goals
2. **Features** — Suggests features based on project type, allows selection
3. **Generate CLAUDE.md** — Creates project specification
4. **Handoff** — Passes to Solution Architect

**Output:** `CLAUDE.md` — Project overview, goals, features

**Key Features:**
- Minimal questions, maximum suggestions
- Smart inference from project description
- Multi-select options with "All of the above" convenience

---

### 2. Solution Architect (`solution-architect`)

**Purpose:** Define technical architecture and specifications.

**Workflow:**
1. **Analyze Requirements** — Review CLAUDE.md
2. **Technology Stack** — Recommend and confirm tech choices
3. **Third-party Integrations** — Identify required SDKs/libraries
4. **Platform Breakdown** — Define platforms for multi-platform projects
5. **Architecture Decisions** — Document key technical decisions
6. **Risk Assessment** — Identify technical risks and mitigations
7. **Generate ARCHITECTURE.md** — Create technical specification

**Output:** `ARCHITECTURE.md` — Tech stack, platforms, architecture, risks

---

### 3. Project Manager (`project-manager`)

**Purpose:** Setup development team, create tasks, and manage project structure.

**Three Main Responsibilities:**

| # | Role | Description |
|---|------|-------------|
| 1 | Add Specifications | Fill gaps in requirements if needed |
| 2 | Setup Team | Create sub-agents with latest best practices (researched online) |
| 3 | Create Tasks | Generate task files with test cases |

**Workflow Modes:**

**First Time (Auto-Guided):**
```
PM: Analyzing project...

Checking: CLAUDE.md ✅ Found
Checking: ARCHITECTURE.md ✅ Found
Checking: .claude/agents/ ❌ Not found
Checking: tasks/ ❌ Not found

Step 1/3: Additional Specifications
Step 2/3: Setup Team  
Step 3/3: Create Tasks
```

**Subsequent Visits (Menu):**
```
1. Add New Features
2. Modify Team
3. View Status
4. Re-generate Tasks
```

**Output:**
- `.claude/agents/{platform}-developer.md` — Platform-specific sub-agents
- `.claude/agents/qa.md` — QA sub-agent
- `tasks/TASKS-{platform}.md` — Tasks with test cases
- `{project-name}/{platform}/` — Code folders

---

## Sub-Agents (Created by Project Manager)

Sub-agents are project-specific workers created dynamically by the Project Manager.

### Dynamic Best Practices

Sub-agents are NOT hardcoded. For any tech stack, PM:

1. **Detects tech** from ARCHITECTURE.md
2. **Searches online** for latest best practices
3. **Creates agent** with researched patterns

**Search queries executed:**
```
"{tech} architecture pattern best practices {current_year}"
"{tech} recommended project structure {current_year}"
"{tech} coding standards style guide"
"{tech} recommended libraries ecosystem {current_year}"
"{tech} testing best practices"
```

**Example:** For Go + Gin backend:
```
Searching: "Go Gin architecture pattern best practices 2025"
Searching: "Go recommended project structure 2025"
...
✅ Created: .claude/agents/backend-developer.md
```

### Agent Naming Convention

| Platform Type | Agent File |
|---------------|------------|
| Backend (any tech) | `backend-developer.md` |
| Frontend (any tech) | `frontend-developer.md` |
| iOS (any tech) | `ios-developer.md` |
| Android (any tech) | `android-developer.md` |
| Mobile cross-platform | `mobile-developer.md` |
| Admin/Dashboard | `admin-developer.md` |
| QA (all platforms) | `qa.md` |

---

## Task Structure

Tasks are stored in `tasks/TASKS-{platform}.md` with test cases and issues in the same file:

```markdown
## Module: Authentication

### TASK-BE-003: Implement user registration
- **Priority:** High
- **Size:** M (2-4 hours)
- **Dependencies:** TASK-BE-002
- **Status:** ⬜ Pending
- **Description:** POST `/api/auth/register` endpoint
- **Acceptance Criteria:**
  - [ ] Validates email format
  - [ ] Validates password strength
  - [ ] Hashes password with bcrypt
  - [ ] Returns JWT token

#### Test Cases
| ID | Scenario | Expected | Status |
|----|----------|----------|--------|
| TC-BE-003-1 | Valid registration | 201, returns JWT | ⬜ |
| TC-BE-003-2 | Duplicate email | 409 error | ⬜ |
| TC-BE-003-3 | Weak password | 400 error | ⬜ |

#### Issues
_No issues_
```

### Cross-Platform Dependencies

When frontend depends on backend:

```markdown
### TASK-FE-005: Build login form
- **Dependencies:** TASK-BE-004@backend
```

Format: `{TASK-ID}@{platform}`

### Task Status Flow

```
⬜ Pending → 🔄 In Progress → ✅ Done → ✅ Verified
                                │
                                ▼ (if QA finds issue)
                           🔴 Has Issues → 🟡 Fixed → ✅ Verified
```

---

## Development Workflow

### Developer Flow

```
@backend-developer start

backend-developer:
  1. Reads tasks/TASKS-backend.md
  2. Picks task with no blockers
  3. Implements in {project-name}/backend/
  4. Updates task status: ⬜ → ✅
  5. Continues to next task
```

### QA Flow

```
@qa start

qa:
  1. Reads all TASKS-*.md files
  2. Finds tasks with status ✅ Done
  3. Executes test cases
  4. If pass → marks ✅ Verified
  5. If fail → logs issue in same task file
```

### Bug Fix Cycle

```
QA logs issue → Developer fixes → QA verifies
     │                │                │
     ▼                ▼                ▼
Status: 🔴 Open → 🟡 Fixed → ✅ Verified
```

---

## Complete Workflow Example

**Step 1: Business Analyst**
```
Developer: I want to build a project collaboration tool called TeamBoard

BA: Based on your description, here are typical User Management features:
    1. Registration/Login
    2. Profile management
    3. Password reset
    4. All of the above
    
Developer: 4

[Generates CLAUDE.md]
```

**Step 2: Solution Architect**
```
Architect: Reviewing CLAUDE.md...

Recommended tech stack:
- Backend: Node.js + Express + TypeScript
- Frontend: React + TypeScript + Vite
- Database: PostgreSQL

[Generates ARCHITECTURE.md]
```

**Step 3: Project Manager**
```
PM: Setting up project...

Step 1/3: Additional Specifications ✅
Step 2/3: Setup Team
  • Researching Node.js Express best practices...
  ✅ Created: .claude/agents/backend-developer.md
  • Researching React TypeScript best practices...
  ✅ Created: .claude/agents/frontend-developer.md
  ✅ Created: .claude/agents/qa.md
  ✅ Created: teamboard/backend/
  ✅ Created: teamboard/frontend/

Step 3/3: Create Tasks
  ✅ Created: tasks/TASKS-backend.md (12 tasks)
  ✅ Created: tasks/TASKS-frontend.md (15 tasks)

Project setup complete!
```

**Step 4: Development**
```
@backend-developer start

backend-developer:
  Starting TASK-BE-001: Setup project structure
  ✅ Created package.json, tsconfig.json, folder structure
  Status: ⬜ → ✅
  
  Next: TASK-BE-002
```

**Step 5: QA**
```
@qa start

qa:
  Testing TASK-BE-003: User registration
  ✅ TC-BE-003-1: Passed
  ✅ TC-BE-003-2: Passed
  ❌ TC-BE-003-3: Failed (weak password accepted)
  
  Logging issue ISS-BE-003-1...
```

---

## Installation & Usage

### Prerequisites
- Claude AI with skills support
- Access to Claude's computer use capabilities

### Installing Skills

1. Download the `.skill` files:
   - `business-analyst.skill`
   - `solution-architect.skill`
   - `project-manager.skill`
2. Upload to your Claude skills directory
3. Skills will be available in your Claude conversations

### Using MAflow

**Start a new project:**
```
You: I want to start a new project

Claude: [Activates business-analyst skill]
What's the name of your project?
```

**Setup project structure:**
```
You: Setup the project

Claude: [Activates project-manager skill]
[Reads CLAUDE.md and ARCHITECTURE.md]
[Creates sub-agents and task files]
```

---

## Design Principles

### 1. Minimal Input, Maximum Output
Skills infer as much as possible from context, reducing developer burden.

### 2. Dynamic Best Practices
Sub-agents research latest best practices online — no hardcoded patterns.

### 3. Document-Driven
All decisions and progress tracked in markdown files — the source of truth.

### 4. Clear Ownership
- BA owns: CLAUDE.md (business requirements)
- Architect owns: ARCHITECTURE.md (technical specs)
- PM owns: Sub-agents, tasks
- Developers own: Code
- QA owns: Test execution, issue logging

### 5. Everything in One Place
Tasks, test cases, and issues all live in the same file — no context switching.

---

## Demo

[![Watch the Demo](https://img.youtube.com/vi/b2vwoGPmodg/maxresdefault.jpg)](https://www.youtube.com/watch?v=b2vwoGPmodg)

---

## Roadmap

- [x] Business Analyst skill
- [x] Solution Architect skill
- [x] Project Manager skill
- [ ] Integration with external tools (GitHub, Jira)
- [ ] Progress dashboard generation

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