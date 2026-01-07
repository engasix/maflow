# Task Template

Template for creating task files in `tasks/TASKS-{platform}.md`.

---

## Task File Structure

```markdown
# {Project Name} — {Platform} Tasks

> Platform: {Platform Name}
> Tech: {Technology Stack}
> Agent: [{platform}-developer](../.claude/agents/{platform}-developer.md)
> Source: [CLAUDE.md](../CLAUDE.md) | [ARCHITECTURE.md](../ARCHITECTURE.md)
> Code: [{project-name}/{platform}/](../{project-name}/{platform}/)

---

## Summary

| Module | Tasks | Status |
|--------|-------|--------|
| {Module 1} | {count} | ⬜ 0/{count} |
| {Module 2} | {count} | ⬜ 0/{count} |
| **Total** | **{total}** | **0/{total}** |

---

## Module: {Module Name}

### TASK-{PF}-001: {Task Title}
- **Priority:** High | Medium | Low
- **Size:** S (1-2h) | M (2-4h) | L (4-8h) | XL (8h+)
- **Dependencies:** None | TASK-{PF}-XXX | TASK-{PF}-XXX@{other-platform}
- **Status:** ⬜ Pending
- **Description:** {Brief description of what needs to be done}
- **Acceptance Criteria:**
  - [ ] {Criterion 1}
  - [ ] {Criterion 2}
  - [ ] {Criterion 3}

#### Test Cases
| ID | Scenario | Expected | Status |
|----|----------|----------|--------|
| TC-{PF}-001-1 | {Test scenario} | {Expected result} | ⬜ |
| TC-{PF}-001-2 | {Test scenario} | {Expected result} | ⬜ |

#### Issues
_No issues_

---
```

---

## Task ID Format

| Platform | Prefix | Example |
|----------|--------|---------|
| Backend | BE | TASK-BE-001 |
| Frontend | FE | TASK-FE-001 |
| iOS | IOS | TASK-IOS-001 |
| Android | AND | TASK-AND-001 |
| Mobile | MOB | TASK-MOB-001 |
| Admin | ADM | TASK-ADM-001 |

---

## Dependency Format

### Same Platform
```markdown
- **Dependencies:** TASK-BE-002
```

### Multiple Same Platform
```markdown
- **Dependencies:** TASK-BE-002, TASK-BE-003
```

### Cross-Platform
```markdown
- **Dependencies:** TASK-BE-004@backend
```

### Mixed
```markdown
- **Dependencies:** TASK-FE-001, TASK-BE-004@backend
```

---

## Status Values

### Task Status
| Status | Icon | Meaning |
|--------|------|---------|
| Pending | ⬜ | Ready to start |
| Blocked | 🚫 | Waiting for dependency |
| In Progress | 🔄 | Being worked on |
| Done | ✅ | Completed by developer |
| Has Issues | 🔴 | QA found problems |
| Fixed | 🟡 | Developer fixed issues |
| Verified | ✅ | QA confirmed working |

### Test Case Status
| Status | Icon | Meaning |
|--------|------|---------|
| Not Tested | ⬜ | Pending |
| Passed | ✅ | Test passed |
| Failed | ❌ | Test failed |

### Issue Status
| Status | Icon | Meaning |
|--------|------|---------|
| Open | 🔴 | New issue |
| Fixed | 🟡 | Developer fixed |
| Verified | ✅ | QA confirmed |
| Reopened | 🔴 | Fix didn't work |

---

## Size Guidelines

| Size | Hours | Examples |
|------|-------|----------|
| S | 1-2h | Config setup, simple endpoint, UI tweak |
| M | 2-4h | CRUD endpoint, form component, auth flow |
| L | 4-8h | Complex feature, integration, multiple screens |
| XL | 8h+ | Major module, refactoring, complex logic |

---

## Priority Guidelines

| Priority | When to Use |
|----------|-------------|
| High | Core functionality, blockers for other tasks |
| Medium | Important but not blocking |
| Low | Nice-to-have, polish, optimization |

---

## Complete Task Example

```markdown
## Module: Authentication

### TASK-BE-003: Implement user registration
- **Priority:** High
- **Size:** M (2-4 hours)
- **Dependencies:** TASK-BE-002
- **Status:** 🔴 Has Issues
- **Description:** POST `/api/auth/register` endpoint with email/password validation
- **Acceptance Criteria:**
  - [x] Validates email format
  - [ ] Validates password strength
  - [x] Hashes password with bcrypt
  - [x] Creates user in database
  - [x] Returns JWT token
  - [x] Handles duplicate email (409)

#### Test Cases
| ID | Scenario | Expected | Status |
|----|----------|----------|--------|
| TC-BE-003-1 | Valid registration | 201, returns JWT | ✅ |
| TC-BE-003-2 | Duplicate email | 409 error | ✅ |
| TC-BE-003-3 | Invalid email format | 400 error | ✅ |
| TC-BE-003-4 | Weak password | 400 error | ❌ |

#### Issues
| ID | Severity | Description | Status |
|----|----------|-------------|--------|
| ISS-BE-003-1 | High | Weak password accepted | 🔴 Open |

##### ISS-BE-003-1: Weak password accepted during registration
- **Found:** 2025-01-07
- **Test Case:** TC-BE-003-4
- **Steps:** POST /api/auth/register with password "123"
- **Expected:** 400 error with validation message
- **Actual:** 201 success, user created with weak password

**Resolution:**
_Pending fix_

**Verification:**
_Pending_

---
```

---

## Cross-Platform Task Example

```markdown
## Module: Authentication

### TASK-FE-005: Build login form
- **Priority:** High
- **Size:** M (2-4 hours)
- **Dependencies:** TASK-BE-004@backend
- **Status:** 🚫 Blocked
- **Description:** Login form with email/password, validation, and API integration
- **Acceptance Criteria:**
  - [ ] Email input with validation
  - [ ] Password input with show/hide toggle
  - [ ] Form validation before submit
  - [ ] Calls POST /api/auth/login
  - [ ] Stores JWT in secure storage
  - [ ] Redirects to dashboard on success
  - [ ] Shows error message on failure

#### Test Cases
| ID | Scenario | Expected | Status |
|----|----------|----------|--------|
| TC-FE-005-1 | Valid login | Redirects to dashboard | ⬜ |
| TC-FE-005-2 | Invalid credentials | Shows error message | ⬜ |
| TC-FE-005-3 | Empty fields | Shows validation errors | ⬜ |
| TC-FE-005-4 | Network error | Shows connection error | ⬜ |

#### Issues
_No issues_

---
```

---

## Module Organization

Group tasks by feature/module:

```markdown
## Module: Authentication
- TASK-BE-001: Setup project structure
- TASK-BE-002: Setup database connection
- TASK-BE-003: Implement user registration
- TASK-BE-004: Implement user login

## Module: Projects
- TASK-BE-005: Create project model
- TASK-BE-006: Create project CRUD endpoints
- TASK-BE-007: Add team members to project

## Module: Tasks
- TASK-BE-008: Create task model
- TASK-BE-009: Create task CRUD endpoints
- TASK-BE-010: Update task status (Kanban)
```

---

## Foundation Tasks

Always include these at the start:

### Backend
```markdown
### TASK-BE-001: Setup project structure
- **Priority:** High
- **Size:** S (1-2 hours)
- **Dependencies:** None
- **Description:** Initialize project with package.json, TypeScript, ESLint, folder structure
```

### Frontend
```markdown
### TASK-FE-001: Setup project structure
- **Priority:** High
- **Size:** S (1-2 hours)
- **Dependencies:** None
- **Description:** Initialize Vite + React + TypeScript project with folder structure
```

### Mobile
```markdown
### TASK-IOS-001: Setup project structure
- **Priority:** High
- **Size:** S (1-2 hours)
- **Dependencies:** None
- **Description:** Initialize Xcode project with SwiftUI, folder structure, base configuration
```
