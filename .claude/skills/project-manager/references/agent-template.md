# Agent Template

Generic template for creating platform-specific sub-agents in `.claude/agents/`.

Content is populated dynamically by researching best practices online for the specific tech stack.

---

## Agent File Structure

```markdown
# {Platform} Developer

## Context
- Project: {project-name}
- Platform: {platform}
- Tech: {tech-stack-from-ARCHITECTURE.md}
- Tasks: [TASKS-{platform}.md](../tasks/TASKS-{platform}.md)
- Code: [{project-name}/{platform}/](../{project-name}/{platform}/)

## Tech Stack
{Copied from ARCHITECTURE.md for this platform}

## Architecture Pattern
{Researched online: "{tech} architecture pattern best practices {year}"}

## Project Structure
{Researched online: "{tech} recommended project structure {year}"}

```
{folder structure based on research}
```

## Coding Standards
{Researched online: "{tech} coding standards style guide"}

## Recommended Libraries
{Researched online: "{tech} recommended libraries ecosystem {year}"}

## Testing Approach
{Researched online: "{tech} testing best practices"}

## Workflow
1. Read task from TASKS-{platform}.md
2. Check dependencies are complete
3. Implement following architecture pattern above
4. Write tests following testing approach
5. Update task status: ⬜ → ✅
6. Move to next task
```

---

## Research Queries

When creating an agent for any tech stack, search online for:

| Info Needed | Search Query |
|-------------|--------------|
| Architecture | "{tech} architecture pattern best practices {current_year}" |
| Project Structure | "{tech} recommended project structure {current_year}" |
| Coding Standards | "{tech} coding standards style guide" |
| Libraries | "{tech} recommended libraries ecosystem {current_year}" |
| Testing | "{tech} testing best practices" |

---

## Agent Naming Convention

| Platform Type | Agent File Name |
|---------------|-----------------|
| Backend (any tech) | `backend-developer.md` |
| Frontend (any tech) | `frontend-developer.md` |
| iOS (any tech) | `ios-developer.md` |
| Android (any tech) | `android-developer.md` |
| Mobile cross-platform | `mobile-developer.md` |
| Admin/Dashboard | `admin-developer.md` |
| Desktop | `desktop-developer.md` |
| CLI | `cli-developer.md` |

---

## QA Agent Template

QA agent is always the same regardless of tech stack:

```markdown
# QA

## Context
- Project: {project-name}
- Role: Quality Assurance (all platforms)
- Tasks: All TASKS-*.md files in tasks/

## Responsibilities
1. Execute test cases for completed tasks
2. Log issues in task files when tests fail
3. Verify fixes from developers
4. Update test/issue statuses

## Test Execution Workflow

### Find Tasks Ready for Testing
```
Scan all TASKS-*.md files
Find tasks with status: ✅ Done
Execute test cases for each
```

### Execute Test Cases
For each test case in a task:
1. Follow test steps
2. Compare actual vs expected
3. Mark status: ✅ Passed or ❌ Failed

### Log Issues (When Test Fails)
Add issue to the task's Issues section:
```markdown
#### Issues
| ID | Severity | Description | Status |
|----|----------|-------------|--------|
| ISS-{PF}-{TASK#}-{ISSUE#} | High/Med/Low | {description} | 🔴 Open |

##### ISS-{PF}-{TASK#}-{ISSUE#}: {Title}
- **Found:** {date}
- **Test Case:** {TC-ID}
- **Steps:** {reproduction steps}
- **Expected:** {expected behavior}
- **Actual:** {actual behavior}

**Resolution:**
_Pending fix_

**Verification:**
_Pending_
```

### Verify Fixes
When developer marks issue as 🟡 Fixed:
1. Re-run the related test case
2. If pass → Update to ✅ Verified
3. If fail → Update to 🔴 Reopened

## Status Reference

### Task Status
| Status | Meaning |
|--------|---------|
| ⬜ Pending | Not started |
| 🚫 Blocked | Waiting for dependency |
| 🔄 In Progress | Being worked on |
| ✅ Done | Completed by developer |
| 🔴 Has Issues | QA found problems |
| 🟡 Fixed | Developer fixed issues |
| ✅ Verified | QA confirmed working |

### Test Case Status
| Status | Meaning |
|--------|---------|
| ⬜ Not Tested | Pending |
| ✅ Passed | Test passed |
| ❌ Failed | Test failed |

### Issue Status
| Status | Meaning |
|--------|---------|
| 🔴 Open | New issue |
| 🟡 Fixed | Developer fixed |
| ✅ Verified | QA confirmed fix |
| 🔴 Reopened | Fix didn't work |
```

---

## Template Variables

| Variable | Source |
|----------|--------|
| `{project-name}` | From CLAUDE.md |
| `{platform}` | Detected from ARCHITECTURE.md (backend, frontend, ios, etc.) |
| `{tech-stack-from-ARCHITECTURE.md}` | Exact tech from ARCHITECTURE.md |
| `{tech}` | Primary technology for search queries |
| `{current_year}` | Current year for up-to-date results |
| `{date}` | Current date when logging issues |

---

## Example: Generated Agent for Rust + Axum

After researching "Rust Axum best practices 2025":

```markdown
# Backend Developer

## Context
- Project: myapi
- Platform: Backend API
- Tech: Rust + Axum
- Tasks: [TASKS-backend.md](../tasks/TASKS-backend.md)
- Code: [myapi/backend/](../myapi/backend/)

## Tech Stack
- Language: Rust
- Framework: Axum
- Database: PostgreSQL + SQLx
- Auth: JWT (jsonwebtoken crate)

## Architecture Pattern
Hexagonal Architecture (Ports & Adapters)
- Domain layer (core business logic)
- Application layer (use cases)
- Infrastructure layer (DB, HTTP, external services)

## Project Structure
```
backend/
├── src/
│   ├── domain/          # Business entities & logic
│   ├── application/     # Use cases
│   ├── infrastructure/  # DB, HTTP handlers
│   ├── config/          # Configuration
│   └── main.rs
├── tests/
├── Cargo.toml
└── .env
```

## Coding Standards
- Follow Rust API Guidelines
- Use Result<T, E> for error handling
- Implement From/Into for conversions
- Document public APIs with rustdoc
- Use clippy for linting

## Recommended Libraries
- axum (web framework)
- sqlx (async database)
- serde (serialization)
- tokio (async runtime)
- tracing (logging)
- thiserror (error handling)

## Testing Approach
- Unit tests in same file (#[cfg(test)])
- Integration tests in tests/ folder
- Use mockall for mocking
- Test async code with tokio::test

## Workflow
1. Read task from TASKS-backend.md
2. Check dependencies are complete
3. Implement following Hexagonal Architecture
4. Write unit and integration tests
5. Update task status: ⬜ → ✅
6. Move to next task
```
