# Project Constitution – Professional Application Builder
*Adopted 2026-03-12*

---

## 1. Vision & Mission
Build a self-contained platform capable of generating **production-grade websites, SaaS applications, analytics dashboards, APIs, and real-time systems** using AI-driven orchestration. The system must be **extensible, disciplined, and user-centric**, delivering polished results with minimal manual effort.

## 2. Scope & Boundaries
| In-Scope | Out-of-Scope |
|---|---|
| Marketing websites, Full-stack web apps, SaaS platforms, Analytics dashboards, Real-time applications (chat, notifications), API services, Admin panels. | Non-Claude AI services, native mobile apps, complex backend services requiring specialized infrastructure. |
| Full SDD lifecycle (Discovery → Architecture → Design → Implementation → Review → Deploy). | Ad-hoc, undocumented workflows. |
| Generated component libraries, page templates, style guides, CI/CD pipelines. | Raw mock-ups without code export. |
| Royalty-free images (Unsplash/Pexels API), user-provided media, placeholder images. | Copyrighted images, paid stock photos, scraped images without licensing. |

## 3. Architecture & Process
- **Orchestrator (Claude Code)** – runs plan-mode, task-list, work-tree isolation; invokes skills via the `Skill` tool.
- **Interview Agent** – runs in discovery mode to capture functional, non-functional, and UI/UX requirements.
- **User Clarification (Pre-Spec)** – MANDATORY use of `AskUserQuestion` tool before spec creation to clarify tech stack, design preferences, website sections, content requirements, and media sources.
- **Skill Library** – each skill implements a single responsibility. Skills are versioned, discoverable, and reusable. See Section 14 for the full list.
- **SDD Engine** – enforces the Software Design & Development (SDD) methodology; stores artefacts in `docs/` (constitution, ADRs, design specs) and `src/` (code). Each project lives in its own folder, which contains the corresponding `spec.md`.

## 4. SDD Methodology – Full Detail
| Phase | Goal | Deliverables |
|---|---|---|
| **Discovery** | Use interview skill to capture stakeholder needs, perform research and discussion. **MANDATORY**: Use `AskUserQuestion` tool to clarify ALL critical decisions before writing spec. | `requirements.md`, interview transcript, user clarifications, first-draft spec. |
| **Architecture** | Define high-level components, data flow, and agent/skill interactions. | `architecture.md`, ADRs. |
| **Design** | Detail UI/UX, component hierarchy, responsive breakpoints, styling tokens. | `design-spec.md`, wireframes, style guide. |
| **Implementation** | Generate code using skills; edit files via `Edit`/`Write`; track tasks with `TaskCreate/Update`. | Source tree, unit tests, CI config. |
| **Review** | Run `simplify` skill, manual review, performance benchmarking. | Review report, updated docs. |
| **Deploy** | Build production bundles; publish to static host or container registry. | Deployment script, CI/CD pipeline. |

Each phase is gated by a **Task** in the internal task list; no later phase starts until the preceding task is marked **completed**.

## 5. Backend Architecture
- **Supported Patterns**: REST APIs, GraphQL APIs, WebSocket services, Event-driven systems.
- **Supported Frameworks**: Python (FastAPI), Node.js
- **Database Support**: PostgreSQL, MongoDB, Redis, Supabase, Firebase.

## 6. Real-Time Systems
- **Supported Technologies**: WebSockets, Socket.io, Server-Sent Events, Firebase Realtime DB, Supabase Realtime, Redis Pub/Sub.
- **Use Cases**: Chat applications, Notifications, Live dashboards, Multiplayer apps.

## 7. Analytics & Data Systems
- **Supported Features**: event tracking, data pipelines, dashboards, charting systems.
- **Tools**: PostgreSQL analytics tables, ClickHouse (optional), Supabase analytics, Chart.js, Recharts, Apache ECharts.

## 8. Authentication & Security
- **Supported Systems**: OAuth, Email/password, Magic links, JWT authentication, Role-based access control (RBAC), Session management.
- **Tools**: Clerk, Supabase Auth, Auth.js, Firebase Auth.

## 9. SaaS Architecture
- **Features**: multi-tenant architecture, subscription billing, team workspaces, usage tracking, role permissions.
- **Integrations**: Stripe, Lemon Squeezy, Paddle.

## 10. Infrastructure
- **Supported Environments**: Vercel, Docker, AWS, Cloudflare, Railway, Supabase.
- **Deployment Types**: Static sites, Serverless apps, Containerized services.

## 11. Testing Standards
- **Required Tests**: unit tests, integration tests, e2e tests.
- **Tools**: Vitest, Jest, Playwright, Cypress.

## 12. Performance Standards
- Code splitting, lazy loading, caching, CDN usage, image optimization, API response caching.

## 13. Observability
- **Monitoring Tools**: Sentry, LogRocket, Datadog, OpenTelemetry.
- **Metrics**: performance, errors, user activity, API latency.

## 14. AI Integration
- **Capabilities**: chatbots, AI search, AI content generation, recommendation systems, semantic search.
- **Models**: Claude, OpenAI, OpenRouter.

## 15. UI Component System
- **Framework**: React component library, reusable UI primitives, design tokens, theme system.
- **Tools**: Tailwind, shadcn/ui, Radix UI.

## 16. Skill Library
- **Core Skills**: `backend-architect`, `database-designer`, `realtime-engineer`, `security-engineer`, `devops-engineer`, `api-designer`, `analytics-engineer`, `saas-architect`, `frontend-design`, `frontend-responsive-design-standards`, `modern-web-design`, `keybindings-help`, `simplify`, `claude-api`, `designing-beautiful-websites`, `award-winning-website`, `fullstack-guardian`, `geo-content-optimizer`, `senior-fullstack`, `seo-content-writer`.

## 17. Product Lifecycle
- Idea → Validation → MVP → Production → Scale

## 18. Project Templates
- SaaS Starter, Analytics Dashboard, Chat App, Portfolio Website, Marketplace, Admin Panel.

## 19. Governance & Quality Gates
- **Steering Committee** – approves new skills, amends the constitution, sets roadmap priorities.
- **Contributor Guidelines** – all changes must follow the SDD process and be recorded as ADRs.
- **Version Control** – `main` holds the stable release; feature work lives on short-lived branches.
- **Quality Gate** – pull requests must pass automated tests, linting, and the `simplify` skill review before merge.

### 19.1 Image & Media Policy
(This section remains the same as the original)

## 20. Roles & Responsibilities
(This section remains the same, with the addition of the new roles from the expanded skill library)

## 21. Extensibility & Future Work
1. **Skill Marketplace** – enable the community to publish new skills.
2. **Multi-Domain Support** – later add e-commerce extensions.
3. **AI-Driven Analytics** – integrate `claude-api` skill for automated performance and accessibility assessments.

## 22. Adoption Checklist
- [ ] Install Claude Code CLI and enable required hooks.
- [ ] Add all skills from the Skill Library.
- [ ] Configure APIs for any selected services (e.g., Unsplash, Stripe).
- [ ] Run the **Interview Agent** to capture initial requirements.
- [ ] **MANDATORY**: Use `AskUserQuestion` to clarify tech stack, design, sections, and content before spec creation.
- [ ] Follow the SDD phases, creating a task for each.
- [ ] Verify all images comply with licensing requirements.
- [ ] Review and sign-off this Constitution by the Steering Committee.
