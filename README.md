# Professional Website Builder

A self-contained platform that orchestrates Claude Code agents and specialized skills to create **high-quality, production-grade websites** with minimal manual effort. Built on the Spec Driven Development (SDD) methodology.

## 🎯 Vision & Mission

Empower anyone to build professional websites by leveraging AI-powered agents and a curated library of reusable skills. The system is **extensible**, **disciplined**, and **user-centric**, delivering polished results through a structured development lifecycle.

**Last Updated**: 2026-03-08

## 🚀 Core Capabilities

- **Automated Discovery** - Interview agent captures requirements, UI/UX preferences, and technical constraints
- **Spec-Driven Development** - Generate comprehensive specifications before writing code
- **Multi-Skill Orchestration** - Coordinate specialized skills for design, development, content, and optimization
- **Quality Assurance** - Built-in code review, simplification, and performance optimization
- **Production Ready** - Generate deployment-ready code with CI/CD pipelines

## 🛠️ Available Skills

### Design & UI/UX
- **`designing-beautiful-websites`** - UX strategy, information architecture, wireframes, UI systems, and visual design
- **`frontend-design`** - Production-grade frontend interfaces with high design quality
- **`frontend-responsive-design-standards`** - Mobile-first, responsive layouts across all screen sizes
- **`modern-web-design`** - 2024-2025 design trends, micro-interactions, and performance-first interfaces
- **`award-winning-website`** - Gaming landing pages with GSAP scroll animations, 3D effects, and video storytelling

### Development
- **`senior-fullstack`** - Comprehensive fullstack development with React, Next.js, Node.js, GraphQL, PostgreSQL
- **`fullstack-guardian`** - Security-focused full-stack applications with layered security at every level
- **`claude-api`** - Build applications using Claude API and Anthropic SDK

### Content & SEO
- **`seo-content-writer`** - SEO-optimized content creation following best practices
- **`geo-content-optimizer`** - Optimize content for AI citation (ChatGPT, Perplexity, Google AI Overviews)

### Utilities
- **`simplify`** - Review code for reuse, quality, and efficiency
- **`keybindings-help`** - Customize keyboard shortcuts and keybindings
- **`browsing-with-playwright`** - Search and download images for websites
- **`loop`** - Run prompts on recurring intervals
- **`find-skills`** - Discover and install additional agent skills

## 📋 Spec Driven Development (SDD) Process

| Phase | Goal | Skills Used |
|-------|------|-------------|
| **Spec Creation** | Draft comprehensive website specification covering requirements, layout, functionality, content strategy, and SEO/GEO optimization | `designing-beautiful-websites`, `seo-content-writer`, `geo-content-optimizer`, `senior-fullstack` |
| **Spec Approval** | Review and approve specification before code generation | — |
| **Implementation** | Generate production code using specialized skills | `fullstack-guardian`, `award-winning-website`, `frontend-design`, `frontend-responsive-design-standards`, `modern-web-design` |
| **Review** | Code quality review, simplification, and performance benchmarking | `simplify` |
| **Deploy** | Build production bundles and publish to hosting platforms | — |

Each phase is gated by tasks in the internal task list. No phase starts until the preceding task is marked **completed**.

## 🏗️ Architecture

- **Orchestrator (Claude Code)** - Runs plan-mode, task-list, worktree isolation; invokes skills via the `Skill` tool
- **Interview Agent** - Captures functional, non-functional, and UI/UX requirements in discovery mode
- **Skill Library** - Single-responsibility skills that are versioned, discoverable, and reusable
- **SDD Engine** - Enforces methodology; stores artifacts in `docs/` (constitution, ADRs, spec.md) and `src/` (code)

Each website project lives in its own folder with a corresponding `spec.md` containing full build instructions.

## 🚀 Quick Start

### Prerequisites
- Claude Code CLI installed
- Git repository initialized
- Required skills installed (see Adoption Checklist)

### Basic Workflow

1. **Run Interview Agent** to capture requirements
   ```
   Use the interview skill to gather project requirements
   ```

2. **Generate Specification**
   ```
   Create spec.md using designing-beautiful-websites, seo-content-writer,
   geo-content-optimizer, and senior-fullstack skills
   ```

3. **Approve Specification**
   ```
   Review and approve the spec.md before implementation
   ```

4. **Implement Website**
   ```
   Generate code using appropriate skills based on project type
   ```

5. **Review & Optimize**
   ```
   Run simplify skill and perform manual review
   ```

6. **Deploy**
   ```
   Build and publish to hosting platform
   ```

## 📁 Project Structure

```
Website-Builder/
├── CLAUDE.md                    # Project constitution and instructions
├── README.md                    # This file
├── docs/                        # Documentation, ADRs, specifications
├── .claude/
│   └── skills/                  # Installed Claude Code skills
│       ├── award-winning-website/
│       ├── designing-beautiful-websites/
│       ├── frontend-design/
│       ├── frontend-responsive-design-standards/
│       ├── fullstack-guardian/
│       ├── geo-content-optimizer/
│       ├── modern-web-design/
│       ├── senior-fullstack/
│       └── seo-content-writer/
└── [project-folders]/           # Individual website projects
    └── spec.md                  # Project specification
```

## 📚 Documentation

- **[CLAUDE.md](CLAUDE.md)** - Project constitution, governance, and SDD methodology
- **[skills-lock.json](skills-lock.json)** - Installed skills registry

## ✅ Adoption Checklist

- [ ] Install Claude Code CLI and enable required hooks
- [ ] Add core skills:
  - `frontend-design`
  - `frontend-responsive-design-standards`
  - `modern-web-design`
  - `simplify`
  - `designing-beautiful-websites`
  - `award-winning-website`
  - `fullstack-guardian`
  - `senior-fullstack`
  - `seo-content-writer`
  - `geo-content-optimizer`
- [ ] Run Interview Agent to capture initial requirements
- [ ] Follow SDD phases, creating a task for each
- [ ] Review and sign-off constitution

## 🎯 Use Cases

- **Landing Pages** - High-converting marketing pages with modern design
- **Gaming Websites** - Interactive experiences with GSAP animations and 3D effects
- **Full-Stack Applications** - Secure web apps with frontend and backend
- **Content Websites** - SEO-optimized sites that rank in search and AI systems
- **Portfolio Sites** - Professional portfolios showcasing work and skills
- **Business Websites** - Corporate sites with responsive design and accessibility

## 🔮 Future Roadmap

1. **Skill Marketplace** - Community-published skills for animation, analytics, etc.
2. **Multi-Domain Support** - Mobile web design and e-commerce extensions
3. **AI-Driven Analytics** - Automated performance and accessibility assessments
4. **Content Strategy** - AI-first content that ranks and gets cited by AI systems

## 🤝 Contributing

All changes must follow the SDD process and be recorded as ADRs. See [CLAUDE.md](CLAUDE.md) for governance and contributor guidelines.

## 📄 License

MIT License - feel free to use and extend this platform!

## 🙏 Credits

Built with Claude Code and powered by Claude Opus 4.6. Follows the Spec Driven Development (SDD) methodology for disciplined, high-quality website creation.
