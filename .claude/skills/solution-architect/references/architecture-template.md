# Architecture Template

Sections to add to CLAUDE.md after technical review by Solution Architect.

---

## Sections to Add

```markdown
---

## Architecture

### Platform Breakdown

{For multi-platform projects, include ASCII diagram}

```markdown
┌─────────────────────────────────────────────────┐
│              System Architecture                │
├─────────────────────────────────────────────────┤
│                                                 │
│  ┌─────────────┐      ┌─────────────┐          │
│  │  Client A   │      │  Client B   │          │
│  │  (Mobile)   │      │   (Web)     │          │
│  └──────┬──────┘      └──────┬──────┘          │
│         │                    │                  │
│         └────────┬───────────┘                  │
│                  ▼                              │
│         ┌─────────────┐                         │
│         │   API       │                         │
│         │  Gateway    │                         │
│         └──────┬──────┘                         │
│                │                                │
│         ┌──────┴──────┐                         │
│         ▼             ▼                         │
│  ┌─────────────┐ ┌─────────────┐               │
│  │  Services   │ │  Database   │               │
│  │             │ │  + Cache    │               │
│  └─────────────┘ └─────────────┘               │
│                                                 │
└─────────────────────────────────────────────────┘
```

**Platforms:**

| Platform | Type | Technology | Description |
|----------|------|------------|-------------|

| Backend API | Service | {e.g., Node.js + Express} | Core business logic and data APIs |
| {Client A} | Mobile | {e.g., React Native} | {Description} |
| {Client B} | Web | {e.g., React} | {Description} |
| Admin Dashboard | Web | {e.g., React} | Operations and management portal |

### Architecture Decisions

| Area | Decision | Rationale |
|------|----------|-----------|

| API Style | {REST / GraphQL / gRPC} | {Why this choice} |
| Authentication | {JWT / OAuth / Session} | {Why this choice} |
| Database | {PostgreSQL / MongoDB / etc.} | {Why this choice} |
| Cache | {Redis / Memcached / None} | {Why this choice} |
| Real-time | {WebSocket / SSE / Polling / None} | {Why this choice} |
| File Storage | {S3 / GCS / Local / None} | {Why this choice} |
| Message Queue | {RabbitMQ / Redis / Kafka / None} | {Why this choice} |

### Technical Risks

| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| {Risk 1} | High/Medium/Low | High/Medium/Low | {Mitigation strategy} |
| {Risk 2} | High/Medium/Low | High/Medium/Low | {Mitigation strategy} |
| {Risk 3} | High/Medium/Low | High/Medium/Low | {Mitigation strategy} |

### API Structure

High-level API endpoint categories:

| Category | Base Path | Description |
|----------|-----------|-------------|
| Auth | `/api/auth/*` | Authentication and authorization |
| Users | `/api/users/*` | User management |
| {Resource} | `/api/{resource}/*` | {Description} |

### Data Models

Core entities and their relationships:

```markdown
┌──────────────┐       ┌──────────────┐
│    User      │       │   {Entity}   │
├──────────────┤       ├──────────────┤
│ id           │       │ id           │
│ email        │──────▶│ user_id (FK) │
│ password     │       │ {field}      │
│ created_at   │       │ {field}      │
└──────────────┘       └──────────────┘
```

**Entities:**

| Entity | Description | Key Fields |
|--------|-------------|------------|
| User | System users | id, email, password, role |
| {Entity} | {Description} | {fields} |

### Non-Functional Requirements

| Requirement | Target | Notes |
|-------------|--------|-------|
| Response Time | < {X}ms | For standard API calls |
| Availability | {X}% | Uptime target |
| Concurrent Users | {X} | Expected peak load |
| Data Retention | {X} days/months | For logs, user data |

---
```

## Guidelines

### When to Include Each Section

| Section | Include When |
|---------|--------------|

| Platform Breakdown | Multi-platform project (>1 client app) |
| Architecture Decisions | Always |
| Technical Risks | Always (even if minimal) |
| API Structure | Project has backend API |
| Data Models | Project has database |
| Non-Functional Requirements | Enterprise/production projects |

### Diagram Style

- Use ASCII art for compatibility
- Keep diagrams simple and readable
- Show data flow direction with arrows
- Group related components

### Decision Rationale

Always explain WHY a decision was made:

- ❌ "Database: PostgreSQL"
- ✅ "Database: PostgreSQL — ACID compliance needed for financial transactions, PostGIS extension for geolocation queries"

### Risk Assessment

Focus on technical risks, not business risks:

- ✅ "Third-party API rate limiting"
- ✅ "Database scalability under load"
- ❌ "Competitor launches similar product"
- ❌ "Budget overrun"
  