# Project Constitution – Professional‑Website‑Builder
*Adopted 2026‑03‑07*

---

## 1. Vision & Mission
Build a self‑contained platform that lets anyone create **high‑quality, production‑grade websites** by orchestrating Claude Code agents and a curated set of reusable skills. The system must be **extensible**, **disciplined**, and **user‑centric**, delivering polished results with minimal manual effort.

## 2. Scope & Boundaries
| In‑Scope | Out‑of‑Scope |
|----------|--------------|
| Claude Code as orchestrator, interview agent for discovery, and the skills: `frontend‑design`, `frontend‑responsive‑design‑standards`, `modern‑web‑design`, `keybindings‑help`, `simplify`, `claude‑api`, `designing‑beautiful‑websites`, `award‑winning‑website`, `fullstack‑guardian`, `geo‑content‑optimizer`, `senior‑fullstack`, `seo‑content‑writer`. | Non‑Claude AI services, native mobile apps, unrelated backend services. |
| Full SDD lifecycle (Discovery → Architecture → Design → Implementation → Review → Deploy). | Ad‑hoc, undocumented workflows. |
| Generated component libraries, page templates, style guides, CI/CD pipelines. | Raw mock‑ups without code export. |
| Royalty-free images (Unsplash/Pexels API), user-provided media, placeholder images. | Copyrighted images, paid stock photos, scraped images without licensing. |

## 3. Architecture & Process
- **Orchestrator (Claude Code)** – runs plan‑mode, task‑list, work‑tree isolation; invokes skills via the `Skill` tool.
- **Interview Agent** – runs in discovery mode to capture functional, non‑functional, and UI/UX requirements.
- **User Clarification (Pre-Spec)** – MANDATORY use of `AskUserQuestion` tool before spec creation to clarify tech stack, design preferences, website sections, content requirements, and media sources.
- **Skill Library** – each skill implements a single responsibility (design, responsiveness, modern UI, keybindings, simplification, API integration, fullstack development, SEO/GEO optimization, content writing). Skills are versioned, discoverable, and reusable.
- **SDD Engine** – enforces the Software Design & Development (SDD) methodology; stores artefacts in `docs/` (constitution, ADRs, design specs) and `src/` (code). Each website project lives in its own folder; the folder name is the website identifier and contains the corresponding `spec.md` with full instructions for building that website.

## 4. SDD Methodology – Full Detail

| Phase | Goal | Deliverables |
|-------|------|--------------|
| **Discovery** | Use interview skill to capture stakeholder needs, perform research and discussion. **MANDATORY**: Use `AskUserQuestion` tool to clarify ALL critical decisions before writing spec: (1) Tech stack preferences (framework, styling, hosting), (2) Design preferences (colors, typography, style), (3) Website sections (Home, About, Services, Contact, etc.), (4) Content requirements, (5) Features and functionality. Then produce first‑draft specification. | `requirements.md`, interview transcript, user clarifications, first‑draft spec. |
| **Architecture** | Define high‑level components, data flow, and agent/skill interactions. | `architecture.md`, ADRs. |
| **Design** | Detail UI/UX, component hierarchy, responsive breakpoints, styling tokens. | `design-spec.md`, wireframes, style guide. |
| **Implementation** | Generate code using skills; edit files via `Edit`/`Write`; track tasks with `TaskCreate/Update`. | Source tree, unit tests, CI config. |
| **Review** | Run `simplify` skill, manual review, performance benchmarking. | Review report, updated docs. |
| **Deploy** | Build production bundles; publish to static host or container registry. | Deployment script, CI/CD pipeline. |

Each phase is gated by a **Task** in the internal task list; no later phase starts until the preceding task is marked **completed**.

### 4.1 Pre-Spec Clarification Requirements

Before writing any `spec.md`, you MUST use the `AskUserQuestion` tool to clarify:

1. **Tech Stack**
   - Framework preference (Next.js, Astro, React, Vue, static HTML)
   - Styling approach (Tailwind, CSS Modules, Styled Components, vanilla CSS)
   - Hosting platform (Vercel, Netlify, GitHub Pages, custom)
   - CMS needs (Markdown, Headless CMS, database)

2. **Design & Branding**
   - Primary brand colors (or color scheme preference)
   - Typography preferences (modern, classic, playful, professional)
   - Design style (minimalist, bold, corporate, creative, gaming)
   - Logo and brand assets availability

3. **Website Structure**
   - Required sections/pages (Home, About, Services, Portfolio, Blog, Contact, etc.)
   - Navigation structure (single page, multi-page, mega menu)
   - Special features (forms, galleries, testimonials, pricing tables, etc.)

4. **Content & Functionality**
   - Content availability (user provides or AI generates)
   - Interactive features (animations, videos, chatbots)
   - Third-party integrations (analytics, CRM, payment, email)
   - Multilingual requirements

5. **Images & Media**
   - Image sources (user provides, use placeholder, or royalty-free APIs)
   - Video requirements
   - Icon preferences

**CRITICAL**: Never assume answers to these questions. Always ask the user explicitly using `AskUserQuestion` before proceeding to spec creation.

## 5. Governance & Quality Gates
- **Steering Committee** – approves new skills, amends the constitution, sets roadmap priorities.
- **Contributor Guidelines** – all changes must follow the SDD process and be recorded as ADRs.
- **Version Control** – `main` holds the stable release; feature work lives on short‑lived branches (`git checkout -b <feature>`).
- **Quality Gate** – pull requests must pass automated tests, linting, and the `simplify` skill review before merge.

### 5.1 Image & Media Policy

**CRITICAL**: All images and media used in generated websites MUST comply with copyright and licensing laws.

#### Allowed Image Sources
1. **User-Provided Images** – images supplied directly by the user
2. **Royalty-Free APIs** – Unsplash API, Pexels API (free, legal, attribution optional)
3. **Placeholder Services** – placeholder.com, via.placeholder.com (for mockups only)
4. **AI-Generated Images** – DALL-E, Midjourney, Stable Diffusion (if user has access)
5. **Public Domain** – images explicitly marked as public domain

#### Prohibited Image Sources
❌ **NEVER use copyrighted images** without explicit permission
❌ **NEVER use paid stock photos** (Shutterstock, Getty, Adobe Stock) without license
❌ **NEVER scrape images** from random websites using `browsing-with-playwright`
❌ **NEVER use images** from Google Images, Pinterest, or social media without verification

#### Implementation Rules
- When using Unsplash/Pexels API, include proper attribution in code comments
- Always use `alt` text for accessibility
- Optimize all images (WebP/AVIF format, responsive sizes)
- Document image sources in project README or credits section
- If user requests specific images, ask them to provide or confirm licensing

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
- [ ] Add core skills (`frontend‑design`, `frontend‑responsive‑design‑standards`, `modern‑web‑design`, `simplify`, `designing‑beautiful‑websites`, `award‑winning‑website`, `fullstack‑guardian`, `senior‑fullstack`, `seo‑content‑writer`, `geo‑content‑optimizer`).
- [ ] Configure Unsplash API or Pexels API for royalty-free images.
- [ ] Run the **Interview Agent** to capture initial requirements.
- [ ] **MANDATORY**: Use `AskUserQuestion` to clarify tech stack, design, sections, and content before spec creation.
- [ ] Follow the SDD phases, creating a task for each.
- [ ] Verify all images comply with licensing requirements (no copyrighted or paid stock photos).
- [ ] Review and sign‑off this Constitution by the Steering Committee.
