# Portfolio architecture

## Purpose

The portfolio serves two audiences with related but distinct needs:

- **Visitors** need to find relevant work quickly and understand the problem, decisions, and outcomes.
- **The designer maintaining the site** needs a flexible way to publish projects, compose stories, test presentation patterns, and evolve the experience.

The resulting architecture separates content from presentation and treats different kinds of work as different editorial formats.

## Content and navigation

| Surface | Purpose | Design implication |
| --- | --- | --- |
| Home | Establish positioning and invite exploration | An immediate, legible point of view |
| Work | Help visitors scan selected projects | Recognizable titles, strong visual entry points, clear destinations |
| Case studies | Show product reasoning in depth | Flexible storytelling blocks and evidence-led structure |
| Company stories | Provide broader role and organizational context | Connect scope, contributions, and related projects without repetition |
| Lab | Make experiments and prototypes discoverable | Room for different stages of completeness |
| About | Explain experience and working principles | A complementary view of the person behind the work |

## Implementation context

The private production repository uses:

- **React and TypeScript** for the interface
- **TanStack Start and TanStack Router** for application and routing structure
- **Vite and Tailwind CSS** for development and styling
- **Supabase** for parts of the content and application data layer
- **Reusable case-study components** to support varied narratives without custom-building every page
- **Tests** to check aspects of site behavior as the system evolves

This describes the current implementation at a high level, not a contract or an open-source API. Internals may change independently of these documents.

## Interaction principles

1. **Clarity before novelty.** Motion and visual treatments should reinforce understanding, not conceal navigation or require discovery.
2. **Progressive depth.** A visitor can skim the work, then follow a relevant project into deeper detail.
3. **Media with a purpose.** Screenshots, video, and prototypes should demonstrate product behavior or provide evidence.
4. **Accessible alternatives.** Interactive behavior should remain understandable with keyboard input and reduced motion.
5. **Reusable where useful.** Shared conventions keep the site coherent, while individual stories retain room for distinct presentation.

## Public and private boundaries

The live application is maintained in a separate private repository. That source includes the content system and operational configuration used to run the site.

This companion repository does **not** mirror the application or provide a deployable copy. In particular it excludes:

- Server environment variables, credentials, and authentication configuration
- Database structure and migrations
- Unpublished or password-protected case-study content
- Nonpublic client assets and implementation details
- Internal notes, experiments, or drafts not intended for publication

If implementation examples are added, they should be deliberately extracted, reviewed for independence and disclosure risk, and explained in their own context—not copied wholesale from production.

## Maintenance

The live website remains the source of truth for published portfolio content and interactions. This repository is updated selectively when an architectural decision, interaction pattern, or experiment is worth documenting publicly.
