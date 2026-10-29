# Selecting a page section without activating it

A design-to-build example from my portfolio's visual page editor.

**Scope:** The editor foundation merged on October 23, 2026. This is a retrospective of that increment, not a description of every capability in the current editor.

## The problem

The editor renders the portfolio's actual page components so I can select a section in context. Those components also contain working links, buttons, forms, and other visitor interactions.

That creates two different intentions for the same click. On the public site, clicking a contact option should select an inquiry type. In the editor, clicking that area should select the section I want to work on. Allowing both actions can change the page state or submit a form while I am trying to inspect its layout.

The design question was how to preserve a useful view of the real page while making the meaning of interaction predictable.

## Constraints

- Reuse existing page components rather than maintain a separate visual approximation.
- Support section selection from both the sidebar and the rendered page.
- Preserve scrolling, motion, and the ability to inspect narrow layouts.
- Provide keyboard access to section selection.
- Keep normal visitor interactions available in an explicit preview mode.
- Limit the foundation to page inspection and selection. Saving and publishing were separate implementation work.

## Decision: separate selection from visitor interaction

In **Edit**, interaction selects a section and suppresses the underlying activation. In **Preview**, controls behave as they do on the public page.

This makes the mode switch carry a clear responsibility: use Edit to select what to work on; use Preview to interact with the page as a visitor.

| Approach | Tradeoff |
| --- | --- |
| Keep visitor interactions active during selection | Close to the public experience, but a selection attempt can navigate away or trigger an action. |
| Make the rendered page entirely inert | Reduces activation risk, but broad blocking can interfere with scrolling, keyboard use, and inspecting motion. |
| Separate Edit and Preview | Adds an explicit mode switch and interaction rules, while supporting both selection and realistic inspection. |

This table explains the tradeoff retrospectively. It is not a claim that all three alternatives were prototyped or usability-tested.

## Translate the decision into behavior

| Situation | Edit | Preview |
| --- | --- | --- |
| Click a link or button inside a section | Select the section; suppress the underlying action | Allow normal activation |
| Submit a form, including implicit submission from a field | Suppress submission | Allow normal submission |
| Press Enter or Space on a focused section | Select that section | Leave visitor keyboard behavior unchanged |
| Press an arrow key while a section itself has focus | Move between sections | Leave visitor keyboard behavior unchanged |
| Scroll or inspect animation | Preserve those behaviors | Preserve those behaviors |
| Exit full-screen Preview | Return to editing | Escape or Exit preview returns to Edit |

The sidebar and rendered section stay connected: selecting in either place identifies the same section. Full-screen Preview hides editing outlines and the sidebar while retaining the selected page and viewport.

**Preview is interactive.** It should not be treated as a sandbox where submitting a form has no consequences.

## A boundary that mattered during implementation

Blocking pointer clicks alone would leave keyboard submission available. Conversely, blocking every keyboard event would make ordinary inspection harder.

The implementation therefore distinguishes section selection, control activation, form submission, and ordinary input. Arrow keys move between sections only when a section itself has focus. Textarea newlines and ordinary typing remain possible, while submission is suppressed in Edit.

That leaves a deliberate limitation: Tab can still reach controls, and typing can change an input's local value. The foundation prevents normal activation and submission in Edit; it does not make every field immutable. Browser context menus and modifier-key shortcuts are also outside the guard's complete control.

## Evidence and verification

This account was prepared by reviewing the merged implementation record and the corresponding test source. The underlying application is private; this public companion provides a curated explanation rather than production code or internal review links.

| Evidence | What it establishes | Limit |
| --- | --- | --- |
| Merged foundation record | The selection and preview work was merged on October 23, 2026 | Merge status alone does not prove live behavior |
| Test source reviewed for this write-up | Assertions cover pointer selection, Edit submission suppression, keyboard selection, and Preview allowing normal interaction | Reading assertions is not executing them |
| Verification recorded with that increment | Type checking and 18 automated tests were reported passing | Historical results; not rerun for this write-up |
| Browser checks recorded with that increment | Selecting contact controls in Edit did not activate them or submit; Preview restored interaction; Escape returned to Edit | Recorded checks from the implementation environment, not a new production audit |

Some content-backed sections were unavailable in that implementation environment. Those checks do not establish complete visual coverage of every populated page. No usability study, measured reduction in errors, or productivity gain is claimed.

## What this changed

The merged foundation established one shared selection and preview model for the portfolio's system pages. It made the interaction contract explicit enough to implement and check across links, forms, and keyboard input.

It did not complete the page builder. The foundation had no Save or Publish, and adding, removing, or reordering sections was outside that increment. Later editor work should be evaluated separately.

The practical lesson is to define the meaning of an action in each mode, then test the boundary with several input methods. A visually accurate editor also needs a clear interaction contract.

## How this relates to the framework

| Framework document | Applied here |
| --- | --- |
| [Decision log](https://github.com/marianneevett/product-design-practice/blob/main/framework/04-decision-log.md) | Explain why selection and visitor interaction need separate modes. |
| [Feature definition](https://github.com/marianneevett/product-design-practice/blob/main/framework/05-feature-definition.md) | Define pointer, keyboard, submission, and recovery behavior. |
| [Build brief](https://github.com/marianneevett/product-design-practice/blob/main/framework/06-build-brief.md) | Scope the foundation and distinguish verification targets from recorded results. |

These links map the work to a reusable method retrospectively. They do not imply that the original implementation used these exact templates.

[Back to portfolio overview](../README.md) · [Portfolio architecture](architecture.md)
