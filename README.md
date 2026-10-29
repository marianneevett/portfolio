# Marianne Evett — Product Design Portfolio

**Designing through human behavior, complex systems, and business constraints.**

[Explore the portfolio](https://mariannematilda.com) · [Selected work](https://mariannematilda.com/work) · [About](https://mariannematilda.com/about)

This repository is a public-facing companion to my product design portfolio. It documents the thinking and selected implementation patterns behind the site—not a second deployment or a copy of its production source code.

My work spans consumer marketplaces, fintech, commerce, and emerging product ideas. I focus on turning ambiguous problems into useful experiences by connecting customer behavior, product strategy, technical constraints, and measurable outcomes.

## The portfolio

The live site is organized to make both the work and the reasoning accessible:

- **Selected work** — An overview of projects and product experiences, with pathways into deeper stories where available.
- **Case studies** — Context, problem framing, constraints, tradeoffs, design decisions, and outcomes rather than screens without explanation.
- **Company stories** — The broader context of a role, how a product evolved, and selected work within it.
- **Lab** — Experiments, prototypes, and explorations of ideas still taking shape.
- **About** — The experience, principles, and tools that inform my practice.

Some case studies are access-controlled. Their materials are intentionally not reproduced in this repository.

## Design and build approach

I treat my portfolio as a product: its content, interaction patterns, performance, and maintainability are all part of the design.

**Editorial structure.** Clear type hierarchy and selective imagery let the work lead. Project covers and motion serve orientation rather than decoration.

**Evidence and decisions.** The stories prioritize what mattered, what was ruled out, and why. The goal is to make the work understandable beyond the final interface.

**Prototyping in context.** I use design and development tools together to explore concepts, test interactions, and evaluate implementation tradeoffs.

**Reusable systems.** Project presentation, content blocks, and media behaviors are developed as patterns so the portfolio can evolve without becoming a collection of one-off pages.

**Intentional motion.** Animation should help reveal, connect, or explain content—and not become a prerequisite for navigation.

## Applied design decision

[Selecting a page section without activating it](docs/editor-selection-and-preview.md) follows one concrete decision in the portfolio's visual editor: separating section selection from normal links, forms, and keyboard interactions. It connects the tradeoff to implemented behavior, recorded verification, and the limits of that foundation.

The reusable documentation approach is in [Product Design Practice](https://github.com/marianneevett/product-design-practice).

## Technical overview

The private production application uses React, TypeScript, TanStack Start/Router, Vite, Tailwind CSS, and a Supabase-backed content layer. It also includes reusable presentation components and tests.

This repository intentionally excludes production application code, database migrations, environment configuration, credentials, unpublished content, and restricted case-study assets.

For a concise explanation of the system and the reasons for this separation, see [Portfolio architecture](docs/architecture.md).

## What this repository is—and isn't

This is a curated record of the design and technical decisions behind [mariannematilda.com](https://mariannematilda.com). It is **not** a template, the production codebase, or a runnable mirror of the live website.

The documentation can evolve alongside the portfolio without duplicating production infrastructure.

---

**Marianne Evett** · Product Design · [mariannematilda.com](https://mariannematilda.com)
