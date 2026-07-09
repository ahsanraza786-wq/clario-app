# Increment 1 — "Create a Policy, done right"

Status: FINALIZED · Built under Clario Operating Model v1.0

## Design
- Problem: the policy output was a thin "blob," and the "how you work" questions only allowed one answer.
- User: Maya-type operations lead who is not a compliance expert.
- Goal: produce a full, professional, tailored policy + make the AI transparent and trustworthy.

## What we built (Develop)
- Multi-select "how you work" questions (e.g., SSO AND passwords).
- Full multi-section policy generator: Purpose, Scope, Policy (tailored sub-sections), Roles & Responsibilities, Enforcement, Evidence for Audit, Review — for all 6 policy types, each mapped to real SOC 2 / NIST controls.
- AI Trust Panel: "here's what I did" (steps), "where I got it" (trusted official sources), "how sure I am" (Solid / Double-check), and "show your work" (section-to-control mapping), plus the human-approval note — all in plain 7th-grade language.
- Professional inline SVG icon system (Lucide-style) replacing emoji in this flow. No AI clip-art.

## Key decisions (Decision log)
- Icons: inline SVG (no external CDN dependency, reliable, crisp, professional).
- Confidence heuristic: if a "not yet / no process" answer is chosen, that area is written as "we are putting this in place" and flagged in the Trust Panel as "double-check."
- Safety: the AI drafts and shows sources; a human always reviews and approves.

## Test & QA
- JavaScript validated with `node --check` (passes).
- Verified: multi-select toggles; single-select replaces; "Generate" is disabled until every question is answered; all six policies produce full documents; Trust Panel renders sources, confidence, and mapping.
- Design/accessibility: icons use currentColor and scale cleanly; contrast maintained.

## Validate
- Output matches the control requirements it claims (section-to-control mapping shown in the Trust Panel).
- Anything uncertain is flagged for a human, never guessed.

## Definition of Done — met
Works (happy path + gaps) · meets design standards · documented (this file) · validated vs. framework · no secrets/data exposed in this front-end.

## Follow-ups (backlog)
- Progressive: migrate remaining emoji icons across all screens to the SVG set.
- Make it truly live: wire the Claude drafting agent (needs Anthropic API key + a server function) so every policy is uniquely generated, not template-assembled.
