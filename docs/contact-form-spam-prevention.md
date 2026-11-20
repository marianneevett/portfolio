# Contact form: designing for trustworthy access

**Status:** Design and implementation direction; Cloudflare Turnstile is proposed, not verified as shipped.

A portfolio contact form needs to be easy for a recruiter, founder, or collaborator to use while resisting automated submissions. The design decision is to keep the experience small—Name, Email, and Message—while placing most abuse prevention behind the interface.

## The design tension

Visible CAPTCHA challenges can interrupt legitimate inquiries, especially on mobile or with assistive technology. Removing protection altogether, however, can flood the inbox and make meaningful messages harder to identify.

The preferred approach uses layered defenses rather than a single intrusive interaction:

- A hidden honeypot discourages basic automated submissions.
- Server-side validation checks that submitted fields are well formed.
- Rate limiting constrains repeated submissions without adding steps for ordinary visitors.
- Cloudflare Turnstile is the proposed additional verification layer, with a challenge only when needed.

## Interaction principles

**Keep the form direct.** Collect only information needed to respond. Do not require company names, budgets, or project categories.

**Make protection mostly invisible.** Most visitors should be able to submit without solving a puzzle. If verification is needed, it should be keyboard-accessible and work on mobile.

**Explain failures.** Verification failures should offer a retry and an alternative way to make contact, rather than leaving the submit button disabled indefinitely.

**Respect privacy.** Avoid retaining raw visitor IP addresses for abuse prevention; use limited, hashed identifiers and defined retention.

**Preserve replyability.** Transactional notifications should allow a direct reply to the person who submitted the inquiry, while keeping the site's authenticated sending address.

## What this documents

This is a public record of the design reasoning, not production source code or a security guarantee. The production implementation and operational details are maintained separately in the private portfolio repository. Turnstile is a planned enhancement until deployment and testing are confirmed.
