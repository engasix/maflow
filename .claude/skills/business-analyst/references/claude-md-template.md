# CLAUDE.md Template

Use this template when generating the CLAUDE.md file. Adapt sections based on project type.

---

```markdown
# {PROJECT_NAME}

## Overview

{Brief description of what this project does and what problem it solves. 2-3 sentences.}

## Platforms

{List platforms if multi-platform project, e.g.:}
- **Backend API** — Core services and business logic
- **Rider App** — Mobile app for passengers
- **Driver App** — Mobile app for drivers
- **Admin Dashboard** — Web portal for operations

{Or for single platform:}
Single platform: {Web App / Mobile App / API / etc.}

---

## Features

### {Category 1, e.g., Rider Features}
- {Feature 1}
- {Feature 2}
- {Feature 3}

### {Category 2, e.g., Driver Features}
- {Feature 1}
- {Feature 2}
- {Feature 3}

### {Category 3, e.g., Admin Features}
- {Feature 1}
- {Feature 2}

---

## Technology Stack

| Layer | Technology |
|-------|------------|
| Backend | {e.g., Node.js + Express} |
| Frontend | {e.g., React + TypeScript} |
| Mobile | {e.g., React Native} |
| Database | {e.g., PostgreSQL} |
| Cache | {e.g., Redis} |
| Cloud | {e.g., AWS / GCP / Azure} |

{Remove rows not applicable to the project}

---

## Third-party Integrations

| Purpose | Library/SDK |
|---------|-------------|
| {e.g., Payments} | {e.g., Stripe SDK} |
| {e.g., Maps} | {e.g., Google Maps API} |
| {e.g., Notifications} | {e.g., Firebase FCM} |
| {e.g., SMS/OTP} | {e.g., Twilio} |
| {e.g., Real-time} | {e.g., Socket.io} |

{Remove if no third-party integrations needed}

---

## Notes

{Any additional notes, constraints, or preferences mentioned by the developer}
```

---

## Customization Guidelines

**Single Platform Projects:**

- Remove "Platforms" section or simplify to one line
- Features don't need category grouping

**Multi-platform Projects:**

- List all platforms clearly
- Group features by platform/user type
- Tech stack may vary per platform

**No Third-party Integrations:**

- Remove that section entirely

Keep the document concise and focused on what's needed for development.
