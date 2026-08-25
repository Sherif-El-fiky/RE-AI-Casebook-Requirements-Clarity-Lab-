# Case Study 01 — Ambiguous & Underspecified Requirements

**Scenario:** a building access control system (synthetic, domain-neutral — no employer or client data).

## What this demonstrates

A walkthrough of using AI to accelerate ambiguity detection in raw stakeholder input, and — just as importantly — where requirements engineering judgment has to step in to correct, reject, or sharpen what the AI produced. The point isn't "AI found the ambiguity"; it's showing the review process a competent RE applies on top of that output before anything gets called a requirement.

## How to read this

The five files are numbered in the order they're meant to be read:

| File | What it contains |
|---|---|
| [`00-problem-statement.md`](00-problem-statement.md) | The scenario and scope for this case study |
| [`01-raw-stakeholder-input.md`](01-raw-stakeholder-input.md) | Unfiltered stakeholder input, as it would actually arrive — vague, informal, contradictory in places |
| [`02-ai-assisted-analysis.md`](02-ai-assisted-analysis.md) | The AI prompt used, its raw output, and an RE assessment of that output — what it caught, what it missed, what it got wrong |
| [`03-refined-requirements.md`](03-refined-requirements.md) | The final requirements, rewritten to be testable and unambiguous, in CPRE/INCOSE-aligned format |
| [`04-reflection-and-judgment.md`](04-reflection-and-judgment.md) | Explicit notes on where RE judgment overrode or supplemented the AI output — the actual point of this case study |

A UML activity diagram of this process (capture input → AI-assisted scan → RE review → finalize or flag) is included in `00-problem-statement.md`.

## Honesty note

This scenario is synthetic. No client, employer, or project-confidential material appears anywhere in this case study.
