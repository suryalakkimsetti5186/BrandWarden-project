# 🛡️ Brandwarden

**Brand governance before publication.** Brandwarden reviews content against an organisation's approved guidelines, terminology, facts and restricted names, explains every issue it finds, and leaves the final decision to people.

**Live app:** https://brandwarden.vercel.app/

## The problem

Content now comes from employees, agencies and AI tools, often under deadline. Wrong figures, unsupported claims, inconsistent language, leaked internal names and inaccessible copy are usually caught late by an overloaded reviewer, or not at all. Feedback like "this feels off-brand" gives creators nothing to act on.

## How it works

1. **Create content.** Paste a draft or load one of the built-in samples (social post, press release, blog).
2. **Automated check.** The text is checked against the brand knowledge base. Each finding shows its category, severity, the reason, the guideline it comes from, and a suggested fix.
3. **Human decision.** Accept a fix, dismiss it with a recorded reason, or edit the text yourself. Nothing is applied automatically.
4. **Review and approval.** Submitting routes the draft by risk: high-risk findings (incorrect facts, absolute claims, confidential names) go to a Reviewer, everything else to a Manager. Reviewers and managers can comment, request changes, escalate or approve.
5. **Traceability.** Every version is stored with a word-level diff, and each action is written to an audit log.
6. **Insights.** See which rules are broken most often and which guidelines people keep dismissing, a sign the wording may be unclear.

## What it checks

| Category | Examples |
|---|---|
| Terminology | Product naming, preferred and banned terms |
| Facts | Prices, counts and metrics compared with an approved fact sheet; expired entries are flagged |
| Claims | Superlatives and absolutes ("best", "guaranteed", "100%") without evidence |
| Tone | Exclamation marks, ALL-CAPS, hype language, emoji by channel |
| Confidentiality | Restricted internal names |
| Accessibility | Missing alt text, vague link text, long sentences, lowercase hashtags, readability score |

## Roles

| Role | Can do |
|---|---|
| Creator | Edit drafts, resolve findings, submit for review |
| Manager | Review and approve standard content, request changes, escalate |
| Reviewer | Approve any content, including high-risk items |

## Knowledge base

The knowledge base is editable in the app: terminology, approved facts with owners' review dates, and restricted names. Changes apply to the next check immediately.

## Responsible design

- **Human control.** Suggestions are never applied without a click. High-risk content always needs an authorised reviewer.
- **Explainability.** Every finding names the rule involved and explains why it was raised.
- **Confidentiality.** Rule and fact checks run locally in the browser. Restricted names are redacted before any text is sent to an AI service.
- **AI disclosure.** AI features are optional, clearly labelled, and advisory only.

## Tech

- Single-file web app in HTML, CSS and vanilla JavaScript, with no build step.
- Rule and fact engine implemented in the browser (pattern rules, fact-sheet comparison with expiry dates, WCAG-style accessibility checks, Flesch readability).
- Optional AI rewrite and messaging review through Claude, when available in the host environment.
- State stored in the browser via `localStorage`.

## Run locally

Open `brandwarden.html` in any modern browser. No installation required.

## Limitations

- Roles are simulated with a role switcher and are not backed by authentication.
- Data is stored per browser and is not shared between users.
- Supports text content. Image, PDF and DOCX review and guideline import are not yet implemented.

## Roadmap

- Image, PDF and DOCX review, with guideline import from documents.
- Server-side storage with real accounts, SSO and enforced roles.
- Evidence-backed claim verification with measured precision and recall.
- Chat and document-editor integrations (Slack, Google Docs).