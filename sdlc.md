# Software Development Life Cycle (SDLC) — Guide & Effective Documentation for B.Tech Freshers

Welcome! This example-driven guide to the Software Development Life Cycle (SDLC) and how to produce effective project documentation. It's written for B.Tech freshers who want clear steps, templates, and examples to follow when working on academic or small industry projects.

Table of contents
- Overview
- SDLC: Phases & Purpose
  - 1. Requirement Analysis
  - 2. Feasibility Study
  - 3. System / High-level Design
  - 4. Detailed Design
  - 5. Implementation (Coding)
  - 6. Testing
  - 7. Deployment
  - 8. Maintenance & Support
- Common SDLC Models (when to use)
- Project Roles & Deliverables
- Effective Documentation Principles
- Documentation Templates & Examples
  - Project README (example)
  - Sample Software Requirements Specification (SRS) excerpt
  - Sample Design (UML + architecture)
  - Sample Test Case
  - API Documentation example
  - Changelog / Release Notes example
  - Commit message & branching guidelines
- Documentation Checklist
- Tools & Resources
- Quick Tips for B.Tech Students

---

## Overview
SDLC is the structured process used to build, deliver, and maintain software. It breaks development into phases so teams can plan work, manage quality, and deliver reliable systems. Good documentation throughout the SDLC helps communication, reproducibility, grading (for academics), handover, and maintenance.

---

## SDLC: Phases & Purpose

Each phase below includes what to produce (deliverables), who typically participates, examples, and documentation pointers.

1. Requirement Analysis
- Goal: Understand what the system must do and constraints.
- Activities: Stakeholder interviews, use-case discovery, high-level acceptance criteria.
- Deliverables: SRS / requirements backlog, high-level use cases, prioritization.
- Example documentation snippet:
  - SRS excerpt: "The system shall allow a registered user to add an item to the shopping cart, with quantity and optional coupon code."
- Tips: Use clear, testable statements (use "shall" for requirements). Capture non-functional requirements (performance, security, availability).

2. Feasibility Study
- Goal: Verify technical, economic, and schedule feasibility.
- Activities: Technology evaluation, effort estimation, cost/benefit analysis.
- Deliverables: Feasibility report, recommended tech stack, PoC plan.
- Example: Choose React + Node.js + PostgreSQL for web app after PoC.

3. System / High-level Design
- Goal: Define architecture, modules, data flow, interfaces.
- Activities: Draw diagrams (architecture, component), define APIs, select patterns.
- Deliverables: Architecture diagram, module descriptions, data model (ER diagrams).
- Documentation tip: Include diagrams (PlantUML, Lucidchart, Draw.io) and text describing responsibilities of modules.

4. Detailed Design
- Goal: Translate high-level design into implementable components.
- Activities: Class diagrams, DB schema, API contract details, sequence diagrams.
- Deliverables: Detailed design document, API contract (request/response format), DB migration plan.
- Example: `POST /api/cart` request body example and validation rules.

5. Implementation (Coding)
- Goal: Build the software.
- Activities: Coding, code reviews, unit tests, continuous integration.
- Deliverables: Source code, unit tests, build scripts, README.
- Documentation tip: Maintain an up-to-date README in repo root explaining how to build/run locally.

6. Testing
- Goal: Validate functionality, performance, security.
- Activities: Unit, integration, system, acceptance, performance, security tests.
- Deliverables: Test plan, test cases, test reports, bug reports.
- Example test case written below.

7. Deployment
- Goal: Release software to production or user environment.
- Activities: Deployment scripts, CI/CD pipelines, environment configuration.
- Deliverables: Deployment guide, rollback plan, environment variables documentation.
- Tip: Document step-by-step deployment and required infra (ports, DNS, certs).

8. Maintenance & Support
- Goal: Fix bugs, update features, and support users.
- Activities: Incident management, patch releases, feature enhancements.
- Deliverables: Release notes, changelog, support documentation, architecture decision records (ADR).
- Tip: Keep a CHANGELOG.md and an issues backlog with priorities.

---

## Common SDLC Models (brief)
- Waterfall: Sequential; good for well-understood projects (low change). Easy to document phase-by-phase.
- Iterative / Incremental: Build in cycles; good for complex systems.
- Agile (Scrum, Kanban): Continuous delivery, frequent feedback. Document user stories, acceptance criteria, sprint reports.
- V-Model: Emphasizes corresponding testing phase for each development phase.
- DevOps / Continuous Delivery: Automate build/test/deploy; documentation should be living (docs-as-code).

When in doubt for academic projects: use Agile (sprints) or Iterative to show frequent deliverables.

---

## Project Roles & Deliverables (small-team mapping)
- Project Manager / Team Lead: Plan, coordinate, maintain timeline -> project plan, kickoff notes.
- Business Analyst / Requirements Owner: Gather & document requirements -> SRS, user stories.
- Architect / Senior Dev: Design decisions -> architecture doc, ADRs.
- Developers: Implement -> code, unit tests, code comments.
- QA / Tester: Validate -> test plan, test cases, bug reports.
- DevOps / SysAdmin: Deploy & monitor -> deployment scripts, runbooks.

Even if you play multiple roles in a small project, document which role did what.

---

## Effective Documentation Principles
- Audience-first: Who reads this? (maintainers, evaluators, users)
- Purpose & Scope: What this doc covers and what it does not.
- Keep it concise and structured (headings, lists).
- Single source of truth: Keep docs in repo (e.g., docs/ or wiki) and version-controlled.
- Use templates and stick to them.
- Make docs executable: include commands and examples, not just theory.
- Keep docs close to code: README + docs/ + inline comments.
- Use diagrams for systems and sequences; text for detailed rules.
- Update docs as part of the workflow — treat documentation changes like code changes (PRs, reviews).
- Make docs discoverable: link from README to SRS, API docs, deployment guide.

---

## Documentation Templates & Examples

Below are ready-to-use templates and examples you can copy into your project.

A. Project README (example)
```markdown
# Project Title
Short description: what it does and target users.

## Table of Contents
- About
- Features
- Tech Stack
- Quick Start
- Architecture
- API (link)
- Testing
- Contributing
- License

## Quick Start
1. Clone repo: `git clone https://github.com/<you>/<repo>.git`
2. Install: `npm install`
3. Run: `npm start`
4. Visit: `http://localhost:3000`

## Architecture
One-line summary and a link to docs/architecture.md

## Contributing
Follow CONTRIBUTING.md. Use branch naming: `feature/<short-desc>`, `fix/<short-desc>`.
```

B. Sample Software Requirements Specification (SRS) excerpt
```markdown
# SRS — "Mini E-Commerce" (Excerpt)
## 1. Introduction
Purpose: Define requirements for a mini e-commerce web app.

## 2. Functional Requirements
FR-001: User Registration
- The system shall allow a new user to register with name, email, and password.
Acceptance criteria:
- Registration returns 201 Created on success.
- Email must be unique.

FR-002: Add to Cart
- The system shall allow an authenticated user to add items to a cart with quantity.
Acceptance:
- Adding beyond available stock returns 400 with message "Insufficient stock".

## 3. Non-Functional Requirements
NFR-001: Response Time
- 95% of API calls must respond within 500 ms under nominal load.

NFR-002: Security
- Passwords shall be stored hashed (bcrypt with cost >= 12).
```

C. Sample Design (component + simple UML idea)
- Text: "Backend: Node.js Express; Database: PostgreSQL; Frontend: React"
- ASCII/PlantUML example (short):
```text
@startuml
User --> Frontend
Frontend --> Backend : REST API
Backend --> DB : SQL
@enduml
```

D. Sample Test Case
```text
Test Case ID: TC-001
Title: Register a new user
Preconditions: DB empty for test email.
Steps:
1. POST /api/register { "name":"Test User", "email":"test@example.com", "password":"Pass@123" }
Expected:
- Response 201
- Response body contains userId and email "test@example.com"
- User stored in DB with hashed password
Postconditions: Remove test user from DB
```

E. API Documentation Example (OpenAPI / minimal)
```markdown
POST /api/cart
Description: Add item to cart
Request:
{
  "productId": "uuid",
  "quantity": 2
}
Responses:
- 201 Created: { "cartId": "uuid", "items": [...] }
- 400 Bad Request: { "error": "Insufficient stock" }
- 401 Unauthorized
```

F. Changelog / Release Notes
```markdown
# Changelog
## [1.1.0] - 2026-01-01
- Added discount coupon logic
- Improved cart API performance
## [1.0.0] - 2025-12-01
- Initial release with user auth and cart
```

G. Commit Message Template (conventional-like)
```
<type>(<scope>): <short summary>

<body> (optional)
- bullet list of changes
- issue references: #123

Footer: BREAKING CHANGE: <description>
```
Types: feat, fix, docs, style, refactor, test, chore

H. Branching & Release Strategy (simple)
- main (production-ready)
- develop (integration)
- feature/<name> (for each feature)
- hotfix/<name> (for urgent fixes on main)
Pull requests must include: description, test steps, reviewers.

---

## Documentation Checklist (use before submission / handover)
- [ ] Root README exists and explains how to run the project.
- [ ] Requirements documented (SRS or backlog with acceptance criteria).
- [ ] Architecture diagram and design decisions recorded.
- [ ] API documented with sample requests/responses.
- [ ] Tests (unit/integration) exist and can be run via CI.
- [ ] Deployment steps / Dockerfile / infra docs present.
- [ ] CHANGELOG.md and versioning strategy defined.
- [ ] License and contribution guidelines included.
- [ ] Code is linted and has meaningful comments for complex logic.

---

## Tools & Resources
- Documentation & docs-as-code: Markdown, MkDocs, Docusaurus, GitHub Pages
- API docs: OpenAPI/Swagger, Postman
- Diagrams: PlantUML, Draw.io, Lucidchart
- Testing: Jest, Mocha, PyTest, JUnit
- CI/CD: GitHub Actions, GitLab CI, Jenkins
- Issue tracking / planning: GitHub Issues, Jira, Trello
- Style & linting: ESLint, Prettier, EditorConfig

---

## Quick Tips for B.Tech Students
- Start docs early: write a README and SRS before coding.
- Use simple, clear language: assume the reader is not you.
- Provide commands that a grader can copy-paste to run your project.
- Demonstrate incremental progress: keep a commit history and short commits.
- Keep requirements testable: turn requirements into acceptance tests.
- Use templates — they reduce ambiguity and help structure thinking.
- Cite third-party libraries and their license if used.

---

## "What to Submit" (example for an academic project)
- repository root with:
  - README.md (how to run, features)
  - docs/SRS.md
  - docs/architecture.md (diagrams)
  - src/ (source code)
  - tests/ (test suites)
  - Dockerfile or deployment script
  - CHANGELOG.md
  - LICENSE
  - CONTRIBUTING.md (optional)

---

## Small Example: Minimal README for a Student Project
```markdown
# Mini E-Commerce (Student Project)
A simple web app to demonstrate user registration, product listing, and cart.

## Quick start
1. `git clone https://github.com/your/repo.git`
2. `cd repo`
3. `docker-compose up --build`
4. Open http://localhost:3000

## Run tests
`npm test`

## Project structure
- /src - source
- /docs - SRS and design
- /tests - test cases
```

---

Good luck — document early, iterate often, and keep docs readable and executable!
