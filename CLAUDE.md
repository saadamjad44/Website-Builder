# Project Constitution – Professional‑Website‑Builder
*Adopted 2026‑03‑07*

---

## 1. Vision & Mission
Build a self‑contained platform that lets anyone create **high‑quality, production‑grade websites** by orchestrating Claude Code agents and a curated set of reusable skills. The system must be **extensible**, **disciplined**, and **user‑centric**, delivering polished results with minimal manual effort.

## 2. Scope & Boundaries
| In‑Scope | Out‑of‑Scope |
|----------|--------------|
| Claude Code as orchestrator, interview agent for discovery, and the skills: `frontend‑design`, `frontend‑responsive‑design‑standards`, `modern‑web‑design`, `keybindings‑help`, `simplify`, `claude‑api`, `designing‑beautiful‑websites`, `browsing‑with‑playwright` (for searching and downloading images for websites), `award‑winning‑website`, `fullstack‑guardian`, `geo‑content‑optimizer`, `senior‑fullstack`, `seo‑content‑writer`. | Non‑Claude AI services, native mobile apps, unrelated backend services. |
| Full SDD lifecycle (Discovery → Architecture → Design → Implementation → Review → Deploy). | Ad‑hoc, undocumented workflows. |
| Generated component libraries, page templates, style guides, CI/CD pipelines. | Raw mock‑ups without code export. |

## 3. Architecture & Process
- **Orchestrator (Claude Code)** – runs plan‑mode, task‑list, work‑tree isolation; invokes skills via the `Skill` tool.
- **Interview Agent** – runs in discovery mode to capture functional, non‑functional, and UI/UX requirements.
- **Skill Library** – each skill implements a single responsibility (design, responsiveness, modern UI, keybindings, simplification, API integration, fullstack development, SEO/GEO optimization, content writing). Skills are versioned, discoverable, and reusable.
- **SDD Engine** – enforces the Spec Driven Development (SDD) methodology; stores artefacts in `docs/` (constitution, ADRs, spec.md) and `src/` (code). Each website project lives in its own folder; the folder name is the website identifier and contains the corresponding `spec.md` with full instructions for building that website.

## 4. Spec Driven Development (SDD) – Full Detail

| Phase | Goal | Deliverables | Skills Used |
|-------|------|--------------|-------------|
| **Spec Creation** | Draft the website specification (`spec.md`) outlining requirements, layout, functionality, content strategy, and SEO/GEO optimization. Use `designing‑beautiful‑websites` for UX/UI strategy, `seo‑content‑writer` for content planning, `geo‑content‑optimizer` for AI citation strategy, and `senior‑fullstack` for architecture decisions. | `spec.md` | `designing‑beautiful‑websites`, `seo‑content‑writer`, `geo‑content‑optimizer`, `senior‑fullstack` |
| **Spec Approval** | Review and approve the spec before any code is generated. | Approved `spec.md` | — |
| **Implementation** | Generate code based on the approved spec using skills; edit files via `Edit`/`Write`; track tasks with `TaskCreate/Update`. Use `fullstack‑guardian` for secure full‑stack features, `award‑winning‑website` for gaming/interactive sites, `frontend‑design` for UI components, `frontend‑responsive‑design‑standards` for mobile‑first layouts, and `modern‑web‑design` for 2024‑2025 trends. | Source tree, unit tests, CI config. | `fullstack‑guardian`, `award‑winning‑website`, `frontend‑design`, `frontend‑responsive‑design‑standards`, `modern‑web‑design` |
| **Review** | Run `simplify` skill, manual review, performance benchmarking. | Review report, updated docs. | `simplify` |
| **Deploy** | Build production bundles; publish to static host or container registry. | Deployment script, CI/CD pipeline. | — |

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
| **Designer** | Use `designing‑beautiful‑websites`, `frontend‑design`, `modern‑web‑design` & `award‑winning‑website` to create UI specs. |
| **Developer** | Execute implementation tasks using `fullstack‑guardian` for secure full‑stack features, `senior‑fullstack` for architecture patterns, write unit/integration tests. |
| **Reviewer** | Run `simplify`, perform manual code review, enforce SDD gates. |
| **Ops Engineer** | Maintain CI/CD pipelines, deployment environments. |

## 7. Extensibility & Future Work
1. **Skill Marketplace** – enable the community to publish new skills (e.g., animation, analytics).
2. **Multi‑Domain Support** – later add `mobile‑web‑design` and e‑commerce extensions.
3. **AI‑Driven Analytics** – integrate `claude‑api` skill for automated performance and accessibility assessments.
4. **Content Strategy** – leverage `seo‑content‑writer` and `geo‑content‑optimizer` for AI‑first content that ranks in search engines and gets cited by AI systems (ChatGPT, Perplexity, Google AI Overviews).

## 8. Adoption Checklist
- [ ] Install Claude Code CLI and enable required hooks.
- [ ] Add core skills (`frontend‑design`, `frontend‑responsive‑design‑standards`, `modern‑web‑design`, `simplify`, `designing‑beautiful‑websites`, `award‑winning‑website`, `fullstack‑guardian`, `senior‑fullstack`, `seo‑content‑writer`, `geo‑content‑optimizer`).
- [ ] Run the **Interview Agent** to capture initial requirements.
- [ ] Follow the SDD phases, creating a task for each.
- [ ] Review and sign‑off this Constitution by the Steering Committee.
