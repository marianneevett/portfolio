# Marianne Evett — Product Design Portfolio

**Designing through human behavior, complex systems, and business constraints.**

[Explore selected work](https://marianneevett.com) · [Case studies](https://marianneevett.com/work) · [About](https://marianneevett.com/about)

This repository is a public-facing companion to my product design portfolio. It documents the thinking and selected implementation patterns behind the site—not a second deployment or a copy of its production source code.

My work spans consumer marketplaces, fintech, commerce, and emerging product ideas. I focus on turning ambiguous problems into useful experiences by connecting customer behavior, product strategy, technical constraints, and measurable outcomes.

## The portfolio

The live site is organized to make both the work and the reasoning accessible:

- **Selected work** — An overview of projects and product experiences, with pathways into deeper stories where available.
- **Case studies** — Context, problem framing, constraints, tradeoffs, design decisions, and outcomes rather than screens without explanation.
- **Lab** — Experiments, prototypes, and explorations of ideas still taking shape.
- **About** — The experience, principles, and tools that inform my practice.

Case studies are password-protected. Their materials are intentionally not reproduced in this repository.

## Features

### 💬 Conversational Portfolio — Ask Marianne
An interactive AI assistant that helps visitors explore my experience, discover relevant work, and ask questions about my design practice.

### 📖 Layered Storytelling
A connected narrative structure that moves from career highlights to company retrospectives and detailed case studies, allowing visitors to choose their depth of exploration.

### 🧪 Interactive Lab
A space for exploring motion, interaction design, reusable components, and emerging product ideas through working experiments.

### 🎨 Contextual Interactions & Motion
Contextual cursor behaviors, touch gestures, ambient gradients, scroll-driven animations, and spatial compositions that support discovery and storytelling, with consideration for reduced-motion preferences.

### 🧩 Modular Content System
Reusable presentation blocks for case studies, product showcases, image compositions, and impact metrics. Shared components and content sources maintain consistency across the portfolio while supporting its continued evolution.

### 🛠️ Visual Page Editor
A custom administrative experience for managing pages, arranging content sections, previewing responsive layouts, and publishing or restoring revisions without modifying application code.

### 🔐 Content & Access Management
Session-based access to confidential case studies, draft and published content states, revision history, and centralized asset management.

### 📬 Contact & Professional Inquiries
A dedicated contact experience supported by server-side validation, automated spam prevention, rate limiting, and email notifications.

### 🌙 Theme System
Automatic dark/light mode detection with manual toggle and localStorage persistence.


## Design & Build Approach

I treat my portfolio as a product: its content, interaction patterns, performance, and maintainability are all part of the design.

- **Editorial structure** — Clear visual hierarchy and selective imagery let the work lead.
- **Evidence-led storytelling** — Context, constraints, tradeoffs, and outcomes take precedence over isolated screens.
- **Prototyping in context** — Design and development work together to explore ideas, validate interactions, and evaluate implementation tradeoffs.
- **Reusable systems** — Shared components and content patterns support consistency and continued evolution.
- **Intentional motion** — Animation supports orientation, discovery, and storytelling without interfering with usability.

### Further Reading

- [Portfolio architecture](docs/architecture.md)
- [Design decision: Section selection and interactive previews](docs/editor-selection-and-preview.md)
- [Product Design Practice](https://github.com/marianneevett/product-design-practice) — My broader approach to product design, documentation, and development.

## Technical overview

The private production application uses React, TypeScript, TanStack Start/Router, Vite, Tailwind CSS, and a Supabase-backed content layer. It also includes reusable presentation components and tests.

This repository intentionally excludes production application code, database migrations, environment configuration, credentials, unpublished content, and restricted case-study assets.

For a concise explanation of the system and the reasons for this separation, see [Portfolio architecture](docs/architecture.md).

### 📁 Project Structure

The production application is organized around reusable components, file-based routing, modular content, and separation of concerns.

```text
portfolio/
├── src/
│   ├── assets/                        # Visual assets and media
│   ├── components/                    # Reusable UI and presentation components
│   ├── hooks/                         # Shared hooks and interaction behaviors
│   ├── integrations/                  # External service integrations
│   ├── lab/                           # Interactive experiments and prototypes
│   ├── lib/                           # Shared utilities and application logic
│   ├── routes/                        # File-based application routing
│   │   ├── __root.tsx                 # Global application layout
│   │   ├── index.tsx                  # Homepage
│   │   ├── about.tsx                  # About
│   │   ├── contact.tsx                # Contact
│   │   ├── work.index.tsx             # Selected work
│   │   ├── work.$slug.tsx             # Individual case studies
│   │   ├── work.experience.$slug.tsx  # Company retrospectives
│   │   ├── lab.index.tsx              # Interactive Lab
│   │   ├── lab.$slug.tsx              # Individual experiments
│   │   └── ...                       # Additional application routes
│   ├── router.tsx                     # Router configuration
│   ├── routeTree.gen.ts               # Generated route tree
│   ├── server.ts                      # Server-side application entry
│   ├── start.ts                       # Application initialization
│   └── styles.css                     # Global styles and motion
├── docs/                              # Architecture and design documentation
└── README.md                          # Project overview
```

The application uses TanStack Router's file-based routing to support dynamic case studies, company retrospectives, interactive experiments, and content management.

Production source code remains private. This simplified structure illustrates the application architecture without exposing internal implementation details.

[Read more about the portfolio architecture →](docs/architecture.md)

The architecture supports an evolving portfolio through shared design patterns, reusable interaction behaviors, and independently managed content.

Production source code remains private. This public repository documents selected design decisions, architectural patterns, and implementation approaches.

[Read more about the portfolio architecture →](docs/architecture.md)


---

**Marianne Evett** · Product Design · [marianneevett.com](https://marianneevett.com)
