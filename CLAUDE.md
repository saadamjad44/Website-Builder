# Project Constitution – Professional‑Website‑Builder
*Adopted 2026‑03‑07*

---

## 1. Vision & Mission
Build a self‑contained platform that lets anyone create **high‑quality, production‑grade websites** by orchestrating Claude Code agents and a curated set of reusable skills. The system must be **extensible**, **disciplined**, and **user‑centric**, delivering polished results with minimal manual effort.

## 2. Scope & Boundaries
| In‑Scope | Out‑of‑Scope |
|----------|--------------|
| Claude Code as orchestrator, interview agent for discovery, and the skills: `frontend‑design`, `frontend‑responsive‑design‑standards`, `modern‑web‑design`, `keybindings‑help`, `simplify`, `claude‑api`, `designing‑beautiful‑websites`. | Non‑Claude AI services, native mobile apps, unrelated backend services. |
| Full SDD lifecycle (Discovery → Architecture → Design → Implementation → Review → Deploy). | Ad‑hoc, undocumented workflows. |
| Generated component libraries, page templates, style guides, CI/CD pipelines. | Raw mock‑ups without code export. |

## 3. Architecture & Process
- **Orchestrator (Claude Code)** – runs plan‑mode, task‑list, work‑tree isolation; invokes skills via the `Skill` tool.
- **Interview Agent** – runs in discovery mode to capture functional, non‑functional, and UI/UX requirements.
- **Skill Library** – each skill implements a single responsibility (design, responsiveness, modern UI, keybindings, simplification, API integration). Skills are versioned, discoverable, and reusable.
- **SDD Engine** – enforces the Software Design & Development (SDD) methodology; stores artefacts in `docs/` (constitution, ADRs, design specs) and `src/` (code).

## 4. SDD Methodology – Full Detail

| Phase | Goal | Deliverables |
|-------|------|--------------|
| **Discovery** | Use interview skill to capture stakeholder needs, perform research and discussion, then produce first‑draft specification. | `requirements.md`, interview transcript, first‑draft spec. |
| **Architecture** | Define high‑level components, data flow, and agent/skill interactions. | `architecture.md`, ADRs. |
| **Design** | Detail UI/UX, component hierarchy, responsive breakpoints, styling tokens. | `design-spec.md`, wireframes, style guide. |
| **Implementation** | Generate code using skills; edit files via `Edit`/`Write`; track tasks with `TaskCreate/Update`. | Source tree, unit tests, CI config. |
| **Review** | Run `simplify` skill, manual review, performance benchmarking. | Review report, updated docs. |
| **Deploy** | Build production bundles; publish to static host or container registry. | Deployment script, CI/CD pipeline. |

Each phase is gated by a **Task** in the internal task list; no later phase starts until the preceding task is marked **completed**.

## 5. Governance & Quality Gates
- **Steering Committee** – approves new skills, amends the constitution, sets roadmap priorities.
- **Contributor Guidelines** – all changes must follow the SDD process and be recorded as ADRs.
- **Version Control** – `main` holds the stable release; feature work lives on short‑lived branches (`git checkout -b <feature>`).
- **Quality Gate** – pull requests must pass automated tests, linting, and the `simplify` skill review before merge.

## 6. Roles & Responsibilities
| Role | Responsibilities |
|------|------------------|
| **Product Owner** | Define business goals, prioritize features. |
| **Architect** | Produce architecture ADRs, ensure skill compatibility. |
| **Designer** | Use `frontend‑design` & `modern‑web‑design` to create UI specs. |
| **Developer** | Execute implementation tasks, write unit/integration tests. |
| **Reviewer** | Run `simplify`, perform manual code review, enforce SDD gates. |
| **Ops Engineer** | Maintain CI/CD pipelines, deployment environments. |

## 7. Extensibility & Future Work
1. **Skill Marketplace** – enable the community to publish new skills (e.g., animation, analytics).
2. **Multi‑Domain Support** – later add `mobile‑web‑design` and e‑commerce extensions.
3. **AI‑Driven Analytics** – integrate `claude‑api` skill for automated performance and accessibility assessments.

## 8. Adoption Checklist
- [ ] Install Claude Code CLI and enable required hooks.
- [ ] Add core skills (`frontend‑design`, `frontend‑responsive‑design‑standards`, `modern‑web‑design`, `simplify`).
- [ ] Run the **Interview Agent** to capture initial requirements.
- [ ] Follow the SDD phases, creating a task for each.
- [ ] Review and sign‑off this Constitution by the Steering Committee.
