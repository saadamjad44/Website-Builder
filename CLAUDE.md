# Project Constitution – Professional‑Website‑Builder
*Adopted 2026‑03‑07 | Updated 2026‑03‑08*

---

## 1. Vision & Mission
Build a self‑contained platform that lets anyone create **high‑quality, production‑grade websites** by orchestrating Claude Code agents and a curated set of reusable skills. The system must be **extensible**, **disciplined**, and **user‑centric**, delivering polished results with minimal manual effort.

All generated websites must meet **2026 production standards**: accessible, performant, secure, SEO-optimized, and conversion-focused.

## 2. Scope & Boundaries
| In‑Scope | Out‑of‑Scope |
|----------|--------------|
| Claude Code as orchestrator, interview agent for discovery, and the skills: `frontend‑design`, `frontend‑responsive‑design‑standards`, `modern‑web‑design`, `keybindings‑help`, `simplify`, `claude‑api`, `designing‑beautiful‑websites`, `browsing‑with‑playwright` (for searching and downloading images for websites), `award‑winning‑website`, `fullstack‑guardian`, `geo‑content‑optimizer`, `senior‑fullstack`, `seo‑content‑writer`. | Non‑Claude AI services, native mobile apps, unrelated backend services. |
| Full SDD lifecycle (Discovery → Architecture → Design → Implementation → Review → Deploy). | Ad‑hoc, undocumented workflows. |
| Generated component libraries, page templates, style guides, CI/CD pipelines. | Raw mock‑ups without code export. |
| Production-ready websites with accessibility (WCAG 2.1 AA), performance (Lighthouse >90), SEO (schema + sitemap), security (CSP + validation), analytics integration. | Prototype-only sites without production standards. |
| Multilingual support, CMS integration, conversion optimization, user authentication. | Native mobile apps, desktop applications, blockchain/Web3. |

## 3. Architecture & Process
- **Orchestrator (Claude Code)** – runs plan‑mode, task‑list, work‑tree isolation; invokes skills via the `Skill` tool.
- **Interview Agent** – runs in discovery mode to capture functional, non‑functional, and UI/UX requirements.
- **Skill Library** – each skill implements a single responsibility (design, responsiveness, modern UI, keybindings, simplification, API integration, fullstack development, SEO/GEO optimization, content writing). Skills are versioned, discoverable, and reusable.
- **SDD Engine** – enforces the Spec Driven Development (SDD) methodology; stores artefacts in `docs/` (constitution, ADRs, spec.md) and `src/` (code). Each website project lives in its own folder; the folder name is the website identifier and contains the corresponding `spec.md` with full instructions for building that website.
- **Design System** – unified design tokens (typography scale, spacing scale, color tokens, component standards) ensure visual consistency across all projects.
- **Tech Stack Standard** – default stack enforced unless explicitly overridden in spec (see Section 9).
- **Automation Layer** – automatic Lighthouse audits, accessibility checks, SEO validation, bundle size monitoring, and security scans.

## 4. Spec Driven Development (SDD) – Full Detail

| Phase | Goal | Deliverables | Skills Used |
|-------|------|--------------|-------------|
| **Spec Creation** | Draft comprehensive website specification (`spec.md`) covering ALL mandatory sections (see Section 4.1). Use `designing‑beautiful‑websites` for UX/UI strategy, `seo‑content‑writer` for content planning, `geo‑content‑optimizer` for AI citation strategy, and `senior‑fullstack` for architecture decisions. | `spec.md` with all mandatory sections | `designing‑beautiful‑websites`, `seo‑content‑writer`, `geo‑content‑optimizer`, `senior‑fullstack` |
| **Spec Approval** | Review and approve the spec before any code is generated. Verify all production standards are addressed. | Approved `spec.md` | — |
| **Implementation** | Generate code based on the approved spec using skills; edit files via `Edit`/`Write`; track tasks with `TaskCreate/Update`. Use `fullstack‑guardian` for secure full‑stack features, `award‑winning‑website` for gaming/interactive sites, `frontend‑design` for UI components, `frontend‑responsive‑design‑standards` for mobile‑first layouts, and `modern‑web‑design` for 2024‑2025 trends. | Source tree, unit tests, CI config, automated checks passing. | `fullstack‑guardian`, `award‑winning‑website`, `frontend‑design`, `frontend‑responsive‑design‑standards`, `modern‑web‑design` |
| **Review** | Run `simplify` skill, manual review, automated audits (Lighthouse, accessibility, SEO, security, bundle size). All quality gates must pass. | Review report, audit results, updated docs. | `simplify` |
| **Deploy** | Build production bundles; deploy to staging for final validation; publish to production with rollback capability. | Deployment script, CI/CD pipeline, staging + production environments. | — |

Each phase is gated by a **Task** in the internal task list; no later phase starts until the preceding task is marked **completed**.

### 4.1 Mandatory Spec Sections

Every `spec.md` MUST include these sections:

#### Product Requirements
- **Target Audience** – demographics, psychographics, pain points
- **Business Goals** – revenue targets, lead generation, brand awareness
- **Conversion Goals** – primary and secondary CTAs, success metrics
- **User Journey Map** – entry points, key interactions, conversion funnels
- **CTA Strategy** – placement, copy, hierarchy, A/B test plan

#### Technical Requirements
- **Tech Stack** – framework, styling, animation, hosting, CMS (default or custom)
- **Performance Budget** – LCP < 2.5s, CLS < 0.1, FID < 100ms, JS bundle < 200KB, image optimization (WebP/AVIF)
- **Accessibility Standards** – WCAG 2.1 AA compliance, ARIA labels, keyboard navigation, color contrast validation
- **Security Requirements** – CSP headers, rate limiting, input sanitization, authentication patterns, HTTPS enforcement
- **Browser Support** – target browsers and versions

#### Content Strategy
- **Content Inventory** – pages, sections, word counts
- **SEO Strategy** – target keywords, meta tags, JSON-LD schema, internal linking, sitemap.xml, robots.txt, canonical tags, semantic HTML
- **GEO Strategy** – AI citation optimization for ChatGPT, Perplexity, Google AI Overviews
- **Content Quality** – readability targets, brand tone, fact verification process
- **Multilingual** – languages, localization strategy (if applicable)

#### Design System
- **Typography Scale** – font families, sizes, weights, line heights
- **Spacing Scale** – consistent spacing units (4px, 8px, 16px, etc.)
- **Color Tokens** – primary, secondary, neutral, semantic colors with accessibility ratios
- **Component Standards** – button hierarchy, form elements, cards, navigation patterns
- **Grid System** – breakpoints, container widths, column counts
- **Animation Principles** – timing, easing, performance considerations

#### Features & Components
- **Core Components** – navigation, footer, hero, forms, CTAs
- **Advanced Features** – newsletter signup, cookie consent, search, FAQ schema, blog system, pricing tables, testimonials, portfolio/gallery
- **Interactive Elements** – animations, transitions, micro-interactions
- **Third-Party Integrations** – analytics, CRM, payment, email marketing

#### Analytics & Tracking
- **Analytics Platform** – Google Analytics, Plausible, PostHog, or custom
- **Event Tracking** – button clicks, form submissions, scroll depth, video plays
- **Conversion Tracking** – goal completions, funnel analysis
- **Heatmaps** – user behavior analysis tools (optional)

#### Content Management
- **CMS Strategy** – Markdown files, Git-based CMS, Headless CMS (Contentful, Sanity), or database
- **Content Types** – blog posts, pages, case studies, testimonials
- **Update Workflow** – who updates content, how often, approval process

#### Deployment & DevOps
- **Environments** – Dev → Staging → Production
- **CI/CD Pipeline** – automated tests, build process, deployment triggers
- **Preview Deployments** – branch previews for review
- **Rollback Strategy** – how to revert failed deployments
- **Monitoring** – uptime monitoring, error tracking, performance monitoring

## 5. Production Website Standards

All generated websites MUST meet these non-negotiable standards before deployment:

### 5.1 Accessibility
- **WCAG 2.1 Level AA** compliance mandatory
- **ARIA labels** on all interactive elements
- **Keyboard navigation** fully functional (tab order, focus states, skip links)
- **Color contrast** minimum 4.5:1 for normal text, 3:1 for large text
- **Screen reader** compatibility tested
- **Form labels** and error messages accessible
- **Alt text** on all images (decorative images use empty alt)

### 5.2 Performance
- **Lighthouse Score** ≥ 90 (Performance, Accessibility, Best Practices, SEO)
- **Core Web Vitals**:
  - LCP (Largest Contentful Paint) < 2.5s
  - CLS (Cumulative Layout Shift) < 0.1
  - FID (First Input Delay) < 100ms
- **Bundle Size**:
  - JavaScript < 200KB (gzipped)
  - CSS < 50KB (gzipped)
  - Total page weight < 1MB
- **Images**: WebP/AVIF format, lazy loading, responsive srcset
- **Fonts**: subset, preload critical fonts, font-display: swap

### 5.3 SEO
- **Meta tags**: title (50-60 chars), description (150-160 chars), Open Graph, Twitter Cards
- **Structured data**: JSON-LD schema (Organization, WebSite, Article, Product, etc.)
- **Sitemap.xml**: auto-generated, submitted to search engines
- **Robots.txt**: properly configured
- **Canonical tags**: prevent duplicate content
- **Semantic HTML**: proper heading hierarchy (h1-h6), landmarks
- **Internal linking**: strategic link structure, breadcrumbs
- **Mobile-friendly**: responsive design, mobile-first indexing ready

### 5.4 Security
- **HTTPS**: enforced, HSTS headers
- **CSP (Content Security Policy)**: strict policy, no inline scripts
- **Input validation**: sanitize all user inputs (XSS prevention)
- **Rate limiting**: protect forms and APIs from abuse
- **Authentication**: secure patterns (JWT, OAuth, session management)
- **CSRF protection**: tokens on all state-changing operations
- **Dependency scanning**: no known vulnerabilities in packages
- **Environment variables**: secrets never committed to repo

### 5.5 Analytics & Tracking
- **Analytics platform**: Google Analytics 4, Plausible, or PostHog
- **Event tracking**: button clicks, form submissions, scroll depth, video engagement
- **Conversion tracking**: goal completions, funnel analysis
- **Privacy compliance**: cookie consent, GDPR/CCPA compliance
- **Error tracking**: Sentry or similar for production error monitoring

### 5.6 Content Quality
- **Readability**: Flesch Reading Ease > 60 (8th grade level)
- **Brand consistency**: tone, voice, terminology aligned
- **Fact verification**: claims backed by sources
- **Plagiarism check**: original content only
- **Grammar & spelling**: zero errors in production
- **Content freshness**: dates, statistics, examples current

### 5.7 Browser & Device Support
- **Modern browsers**: Chrome, Firefox, Safari, Edge (last 2 versions)
- **Mobile devices**: iOS Safari, Chrome Android
- **Responsive breakpoints**: mobile (320px+), tablet (768px+), desktop (1024px+)
- **Progressive enhancement**: core functionality works without JS

### 5.8 Deployment Standards
- **Environments**: Dev → Staging → Production (isolated)
- **CI/CD pipeline**: automated tests, builds, deployments
- **Preview deployments**: branch previews for every PR
- **Rollback capability**: one-click revert to previous version
- **Monitoring**: uptime (99.9% SLA), performance, errors
- **Backups**: automated daily backups, tested restore process

## 6. Governance & Quality Gates
- **Steering Committee** – approves new skills, amends the constitution, sets roadmap priorities.
- **Contributor Guidelines** – all changes must follow the SDD process and be recorded as ADRs.
- **Version Control** – `main` holds the stable release; feature work lives on short‑lived branches (`git checkout -b <feature>`).
- **Quality Gate** – pull requests must pass ALL automated checks before merge:
  - Lighthouse score ≥ 90
  - Accessibility audit (axe-core or similar)
  - SEO validation (meta tags, schema, sitemap)
  - Security scan (dependency vulnerabilities, CSP validation)
  - Bundle size check (< 200KB JS, < 50KB CSS)
  - Unit/integration tests passing
  - `simplify` skill review
- **Automated Audits** – run on every commit:
  - `npm run lighthouse` or equivalent
  - `npm run a11y` for accessibility
  - `npm run seo-check` for SEO validation
  - `npm run security-scan` for vulnerabilities
  - `npm run bundle-size` for size monitoring

## 7. Roles & Responsibilities
| Role | Responsibilities |
|------|------------------|
| **Product Owner** | Define business goals, prioritize features. |
| **Architect** | Produce architecture ADRs, ensure skill compatibility. |
| **Designer** | Use `designing‑beautiful‑websites`, `frontend‑design`, `modern‑web‑design` & `award‑winning‑website` to create UI specs. |
| **Developer** | Execute implementation tasks using `fullstack‑guardian` for secure full‑stack features, `senior‑fullstack` for architecture patterns, write unit/integration tests. |
| **Reviewer** | Run `simplify`, perform manual code review, enforce SDD gates, verify all automated audits pass. |
| **Ops Engineer** | Maintain CI/CD pipelines, deployment environments, monitoring, backups. |
| **Content Strategist** | Use `seo‑content‑writer` and `geo‑content‑optimizer` to create conversion-focused, AI-optimized content. |
| **QA Engineer** | Run accessibility audits, performance tests, cross-browser testing, security scans. |

## 8. Default Tech Stack

Unless explicitly overridden in `spec.md`, all projects use this standard stack:

### Frontend
- **Framework**: Next.js 14+ (App Router) or Astro 4+ (for content-heavy sites)
- **Styling**: Tailwind CSS 3+ with custom design tokens
- **Animation**: Framer Motion (React) or GSAP (vanilla JS)
- **Icons**: Lucide Icons or Heroicons
- **Forms**: React Hook Form + Zod validation

### Backend (if needed)
- **Runtime**: Node.js 20+ LTS
- **API**: Next.js API Routes or tRPC
- **Database**: PostgreSQL (Supabase or Neon) or SQLite (Turso)
- **ORM**: Drizzle ORM or Prisma
- **Authentication**: NextAuth.js or Clerk

### Content Management
- **Default**: Markdown files with frontmatter (Git-based)
- **Headless CMS**: Sanity, Contentful, or Payload CMS (for complex needs)
- **Blog**: MDX with syntax highlighting (Shiki)

### Hosting & Deployment
- **Primary**: Vercel (Next.js) or Netlify (Astro)
- **Alternative**: Cloudflare Pages, AWS Amplify
- **CDN**: Automatic via hosting platform
- **Images**: Vercel Image Optimization or Cloudinary

### Analytics & Monitoring
- **Analytics**: Plausible (privacy-first) or Google Analytics 4
- **Error Tracking**: Sentry
- **Uptime**: BetterStack or UptimeRobot
- **Performance**: Vercel Analytics or SpeedCurve

### Development Tools
- **Package Manager**: pnpm (fast, efficient)
- **Linting**: ESLint + Prettier
- **Type Checking**: TypeScript 5+
- **Testing**: Vitest (unit) + Playwright (e2e)
- **Git Hooks**: Husky + lint-staged

### Image Strategy
- **Source**: Unsplash API or Pexels API (royalty-free, legal)
- **Format**: WebP/AVIF with fallbacks
- **Optimization**: Sharp or Vercel Image Optimization
- **Lazy Loading**: Native loading="lazy" or Intersection Observer
- **Responsive**: srcset with multiple sizes

## 9. Unified Design System

All projects inherit these design tokens unless customized in `spec.md`:

### Typography Scale
```css
--font-display: 'Inter', system-ui, sans-serif;
--font-body: 'Inter', system-ui, sans-serif;
--font-mono: 'JetBrains Mono', monospace;

--text-xs: 0.75rem;    /* 12px */
--text-sm: 0.875rem;   /* 14px */
--text-base: 1rem;     /* 16px */
--text-lg: 1.125rem;   /* 18px */
--text-xl: 1.25rem;    /* 20px */
--text-2xl: 1.5rem;    /* 24px */
--text-3xl: 1.875rem;  /* 30px */
--text-4xl: 2.25rem;   /* 36px */
--text-5xl: 3rem;      /* 48px */
```

### Spacing Scale
```css
--space-1: 0.25rem;   /* 4px */
--space-2: 0.5rem;    /* 8px */
--space-3: 0.75rem;   /* 12px */
--space-4: 1rem;      /* 16px */
--space-6: 1.5rem;    /* 24px */
--space-8: 2rem;      /* 32px */
--space-12: 3rem;     /* 48px */
--space-16: 4rem;     /* 64px */
--space-24: 6rem;     /* 96px */
```

### Color Tokens
```css
/* Primary Brand */
--color-primary-50: #eff6ff;
--color-primary-600: #2563eb;
--color-primary-700: #1d4ed8;

/* Neutral */
--color-neutral-50: #fafafa;
--color-neutral-900: #171717;

/* Semantic */
--color-success: #10b981;
--color-warning: #f59e0b;
--color-error: #ef4444;
--color-info: #3b82f6;
```

### Component Standards
- **Buttons**: 3 sizes (sm, md, lg), 3 variants (primary, secondary, ghost)
- **Forms**: consistent input height (40px), focus rings, error states
- **Cards**: 8px border radius, subtle shadow, hover states
- **Navigation**: sticky header, mobile hamburger menu, smooth scroll
- **Grid**: 12-column system, responsive breakpoints

### Breakpoints
```css
--breakpoint-sm: 640px;   /* Mobile landscape */
--breakpoint-md: 768px;   /* Tablet */
--breakpoint-lg: 1024px;  /* Desktop */
--breakpoint-xl: 1280px;  /* Large desktop */
```

## 10. Extensibility & Future Work
1. **Skill Marketplace** – enable the community to publish new skills (e.g., animation, analytics).
2. **Multi‑Domain Support** – later add `mobile‑web‑design` and e‑commerce extensions.
3. **AI‑Driven Analytics** – integrate `claude‑api` skill for automated performance and accessibility assessments.
4. **Content Strategy** – leverage `seo‑content‑writer` and `geo‑content‑optimizer` for AI‑first content that ranks in search engines and gets cited by AI systems (ChatGPT, Perplexity, Google AI Overviews).
5. **E-commerce Support** – Shopify integration, Stripe payments, product catalogs.
6. **Advanced Features** – user authentication, dashboards, real-time features (WebSockets), API integrations.
7. **Internationalization** – multi-language support, RTL layouts, locale-specific content.
8. **A/B Testing** – built-in experimentation framework for conversion optimization.

## 11. Edge Cases & Advanced Scenarios

The system handles these real-world scenarios:

### 11.1 Multilingual Websites
- **i18n routing**: `/en/`, `/es/`, `/fr/` URL structure
- **Content translation**: separate content files per locale
- **SEO**: hreflang tags, locale-specific sitemaps
- **RTL support**: Arabic, Hebrew layout adjustments

### 11.2 Large-Scale Content Sites
- **Pagination**: efficient data fetching for 1000+ pages
- **Search**: Algolia or Meilisearch integration
- **Content organization**: categories, tags, topic clusters
- **Performance**: ISR (Incremental Static Regeneration) for dynamic content

### 11.3 E-commerce Features
- **Product catalogs**: structured data, filtering, sorting
- **Shopping cart**: state management, persistence
- **Checkout**: Stripe or PayPal integration
- **Inventory**: real-time stock updates

### 11.4 User Authentication
- **Sign up/login**: email/password, OAuth (Google, GitHub)
- **Protected routes**: middleware-based access control
- **User profiles**: dashboard, settings, preferences
- **Session management**: secure tokens, refresh logic

### 11.5 SaaS Dashboards
- **Data visualization**: charts, graphs, tables
- **Real-time updates**: WebSockets or Server-Sent Events
- **Role-based access**: admin, user, guest permissions
- **API integration**: REST or GraphQL backends

### 11.6 API Rate Limiting
- **Client-side**: exponential backoff, retry logic
- **Server-side**: rate limiting middleware (express-rate-limit)
- **Caching**: Redis or in-memory cache for frequent requests

### 11.7 CDN & Caching Strategy
- **Static assets**: long-term caching (1 year)
- **Dynamic content**: short-term caching (5 minutes)
- **Cache invalidation**: on-demand purging
- **Edge caching**: Cloudflare or Vercel Edge Network

## 12. Adoption Checklist
- [ ] Install Claude Code CLI and enable required hooks.
- [ ] Add core skills (`frontend‑design`, `frontend‑responsive‑design‑standards`, `modern‑web‑design`, `simplify`, `designing‑beautiful‑websites`, `award‑winning‑website`, `fullstack‑guardian`, `senior‑fullstack`, `seo‑content‑writer`, `geo‑content‑optimizer`).
- [ ] Configure default tech stack (Next.js, Tailwind, Vercel) or customize in project spec.
- [ ] Set up design system tokens (typography, spacing, colors).
- [ ] Configure automated audit tools (Lighthouse, accessibility, SEO, security, bundle size).
- [ ] Set up CI/CD pipeline with quality gates.
- [ ] Configure analytics platform (Plausible or Google Analytics 4).
- [ ] Set up error tracking (Sentry).
- [ ] Configure image optimization (Unsplash/Pexels API).
- [ ] Run the **Interview Agent** to capture initial requirements.
- [ ] Follow the SDD phases, creating a task for each.
- [ ] Verify all production standards are met before deployment.
- [ ] Review and sign‑off this Constitution by the Steering Committee.

---

## Summary of Production-Grade Improvements (v2)

This updated constitution addresses all critical production gaps:

✅ **Product Requirements** – mandatory spec sections for target audience, conversion goals, user journeys, CTA strategy
✅ **Tech Stack Standard** – default Next.js/Astro stack with clear alternatives
✅ **Design System** – unified typography, spacing, color tokens, component standards
✅ **SEO Structure** – comprehensive requirements including schema, internal linking, semantic HTML
✅ **Accessibility** – WCAG 2.1 AA compliance mandatory
✅ **Performance Budget** – Core Web Vitals targets, bundle size limits
✅ **Security Standards** – CSP, input validation, rate limiting, authentication patterns
✅ **Analytics Layer** – platform selection, event tracking, conversion tracking
✅ **Content Quality** – readability, fact verification, plagiarism checks
✅ **CMS Strategy** – Markdown, Git-based, or Headless CMS options
✅ **Image Strategy** – legal sources (Unsplash/Pexels API), optimization, responsive
✅ **Deployment Standards** – Dev → Staging → Production with rollback
✅ **Automated Audits** – Lighthouse, accessibility, SEO, security, bundle size on every commit
✅ **Edge Cases** – multilingual, large-scale content, e-commerce, authentication, SaaS, rate limiting, CDN
✅ **Real-World Components** – newsletter, cookie consent, search, FAQ, blog, pricing, dashboard

The system now produces **truly production-ready websites** that meet 2026 industry standards.
