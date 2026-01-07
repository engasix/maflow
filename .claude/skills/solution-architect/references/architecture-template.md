# ARCHITECTURE.md Template

Complete technical specification. This is the Architect's output file.

---

```markdown
# {PROJECT_NAME} — Architecture

> Technical specification for [{PROJECT_NAME}](./CLAUDE.md)

---

## Technology Stack

| Layer | Technology |
|-------|------------|
| Backend | {e.g., Node.js + Express + TypeScript} |
| Frontend | {e.g., React + TypeScript + Vite} |
| Database | {e.g., PostgreSQL} |
| Cache | {e.g., Redis} |
| Cloud | {e.g., AWS / GCP / Azure} |

---

## Third-party Integrations

| Purpose | Library/SDK |
|---------|-------------|
| {e.g., Authentication} | {e.g., JWT / Auth0} |
| {e.g., Email} | {e.g., SendGrid / AWS SES} |
| {e.g., Real-time} | {e.g., Socket.io} |
| {e.g., File Storage} | {e.g., AWS S3} |

{Remove section if no integrations needed}

---

## Platform Breakdown

{ASCII diagram showing system architecture}

**Platforms:**

| Platform | Type | Technology | Description |
|----------|------|------------|-------------|
| Backend API | Service | {e.g., Node.js + Express} | Core business logic and APIs |
| Frontend | Web | {e.g., React + TypeScript} | User-facing web application |

---

## Architecture Decisions

| Area | Decision | Rationale |
|------|----------|-----------|
| API Style | {REST / GraphQL} | {Why this choice} |
| Authentication | {JWT / Session / OAuth} | {Why this choice} |
| Database | {PostgreSQL / MongoDB} | {Why this choice} |
| Cache | {Redis / None} | {Why this choice} |
| Real-time | {WebSocket / SSE / Polling / None} | {Why this choice} |
| File Storage | {S3 / Local / None} | {Why this choice} |

---

## Technical Risks

| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| {Risk 1} | High/Med/Low | High/Med/Low | {Mitigation strategy} |
| {Risk 2} | High/Med/Low | High/Med/Low | {Mitigation strategy} |

---

## API Structure

| Category | Base Path | Methods | Description |
|----------|-----------|---------|-------------|
| Auth | `/api/auth` | POST | Login, register, logout, refresh |
| Users | `/api/users` | CRUD | User management |
| {Resource} | `/api/{resource}` | {methods} | {Description} |

---

## Data Models

| Entity | Description | Key Fields |
|--------|-------------|------------|
| User | System users | id, email, password_hash, role, created_at |
| {Entity} | {Description} | {key fields} |

---

## Non-Functional Requirements

| Requirement | Target |
|-------------|--------|
| API Response Time | < 200ms |
| Uptime | 99.9% |
| Concurrent Users | {target number} |
```

---

## Guidelines

### When to Include Each Section

| Section | Include When |
|---------|--------------|
| Platform Breakdown | Always (even for single platform) |
| Architecture Decisions | Always |
| Technical Risks | Always (even if minimal) |
| API Structure | Project has backend API |
| Data Models | Project has database |
| Non-Functional Requirements | Production projects |

### Decision Rationale

Always explain WHY a decision was made:
- ❌ "Database: PostgreSQL"
- ✅ "Database: PostgreSQL — ACID compliance needed, strong ecosystem"

### Risk Assessment

Focus on technical risks, not business risks:
- ✅ "Third-party API rate limiting"
- ✅ "Database scalability under load"
- ❌ "Competitor launches similar product"
- ❌ "Budget overrun"
  