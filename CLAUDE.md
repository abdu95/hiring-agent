# Hiring Agent — Recruiter App

B2B web app (mobile + desktop) for recruiters at Urgench RANCH University of Technology and a partner learning centre. Recruiters photograph paper CVs (обективка / маълумотнома, RU/UZ), the app extracts structured fields, the recruiter confirms them, and the app scores each candidate against a vacancy as a transparent percentage.

We are building the **real MVP**, not a throwaway prototype.

## Where the truth lives

- `docs/meetings/` — client meeting notes, local only / gitignored (source context; may be outdated where an ADR or the PRD says otherwise)
- `docs/templates/` — sample обективка (fictional person)
- `GLOSSARY.md` — glossary / ubiquitous language (created during grilling)
- `docs/adr/` — architecture decision records (created during grilling)
- The spec (PRD), created by `/to-spec` in the issue tracker chosen during setup

If these disagree: ADRs and the spec win over meeting notes.

## Product rules (non-negotiable)

- **AI judges → rubric calculates → recruiter decides.** The AI never outputs the overall % score. It extracts facts or answers narrow questions with fixed answer options; a visible, configurable rubric computes the score.
- Scoring only ever runs on **recruiter-confirmed** data, never raw OCR/extraction output.
- Recruiter overrides always win over AI answers and are stored with who/when.
- **Data minimization:** never send name, gender, age/date of birth, photo, nationality, birthplace/home region, marital status, or relatives' data to the AI for judgment/scoring.
- **Synthetic data only** in the repo, tests, and fixtures. Never commit real candidates' documents or personal data.

## How we work

- Use glossary terms from `GLOSSARY.md` in code, UI copy, and conversation. If a new concept appears, add it to the glossary first.
- TypeScript in strict mode. Lean on types, tests, and the browser as feedback loops.
- TDD: write a failing test → make it pass → refactor. Take small steps; don't outrun the feedback.
- Prefer **deep modules**: a lot of functionality behind a small interface. Test at the module interface, not internals.
- Design the interface first; the implementation can be delegated.
- Record significant decisions as ADRs in `docs/adr/`.

## Stack & commands

_To be decided during grilling — fill in after the spec._
