# The Workflow

Based on real-world experience from a software development organization.

---

## Start Here

### 1. Lead Intake
The organization receives a lead.

### 2. Initial Sales Call
A sales agent calls the client and gathers an initial understanding of the project.

### 3. Handover to Business Analyst
The sales agent passes the information to the BA.

### 4. Requirement Analysis & Clarification
The BA analyzes everything and discusses requirements with the architect.

- If there are gray areas, they clarify with the client.
- If something is not possible, they find an acceptable alternate solution.
- This goes back and forth until all requirements are clear.

### 5. Documentation
Once requirements are clear:

- BA creates the project specification (vision, goals, features)
- Architect creates technical specification (tech stack, architecture, risks)

### 6. Proposal Review & Sign-off
The documents are shared with the client.

- Client may ask for changes or clarifications.
- Once signed, the project moves into development.

### 7. Project Manager Assignment
A project manager is assigned to the project.

### 8. Team Setup
The project manager:

- Reviews the signed documents as source of truth
- Determines which platforms need to be developed
- Creates developer agents for each platform
- Creates a QA agent for testing
- Sets up the project folder structure

### 9. Task Creation
The project manager:

- Breaks down features into tasks per platform
- Organizes tasks by modules
- Defines dependencies between tasks
- Adds test cases for each task

### 10. Development
Developers work on their assigned platforms:

- Pick tasks with no blockers
- Check that dependencies are complete before starting
- Implement the code
- Mark tasks as done when complete

### 11. Quality Assurance
QA tests completed tasks:

- Executes test cases
- Logs issues directly in the task file if tests fail
- Includes steps to reproduce and expected vs actual behavior

### 12. Issue Resolution
When QA finds issues:

- Developer fixes the issue
- Developer marks it as fixed with explanation
- QA verifies the fix
- If not fixed, QA reopens the issue

### 13. Deployment
Once all tasks are complete and verified by QA, the project is ready for deployment.

---

## Roles

- **Business Analyst** — Gathers requirements, creates project specification
- **Solution Architect** — Defines technical approach, creates architecture specification
- **Project Manager** — Sets up team, creates tasks, manages workflow
- **Developers** — Implement tasks, fix issues
- **QA** — Tests tasks, logs and verifies issues