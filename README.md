# Brandwarden

Pre-publication brand governance with human control. Built for the Inkloom AI problem statement.

**Live demo:** https://claude.ai/artifact/SQNyXT2LcgRgQXKuYCyVHT

## What it does
Content goes in, is checked against approved brand guidelines, terminology, facts and restricted names, and comes back as explained findings. Each finding cites the rule involved and suggests a fix. A human decides: accept, dismiss with a reason, or send for review.

## Core workflow
1. Create a draft (or load a sample) in **Content**.
2. Review findings: tone, terminology, claims, facts, confidentiality, accessibility.
3. Accept a fix, dismiss it with a reason, or request an AI rewrite (optional, applied only on click).
4. Submit for review. High-risk findings route to a Reviewer; others to a Manager.
5. Switch role to comment, request changes, escalate or approve. Versions, diffs and an audit log are kept.
6. **Insights** shows recurring issues and guidelines that are often dismissed (possibly unclear).

## Tech
- Single-file web app: HTML, CSS and vanilla JavaScript (`brandwarden.html`), no build step.
- Rule and fact engine runs locally in the browser (regex rules, fact sheet with expiry dates, WCAG-style accessibility checks, Flesch readability).
- Optional AI layer: Claude via the claude.ai runtime `sample` capability, for rewrites and messaging review. Restricted names are redacted before sending; output is labelled and never auto-applied.
- Storage: browser `localStorage` (per viewer).

## Limitations (Round 2)
- Roles are a simulated switch, not real authentication.
- No server: data is not shared between users.
- Text only; image, PDF and DOCX review and guideline import are planned.

## Run locally
Open `brandwarden.html` in a browser. AI features appear only inside the claude.ai runtime.

## Round 3 plan
1. Document and image review, plus guideline import from PDF/DOCX.
2. Shared backend with real accounts, SSO and enforced roles.
3. Evidence-backed claim verification with a measured precision/recall evaluation.
