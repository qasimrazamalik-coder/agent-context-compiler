---
name: agent-context-compiler
description: Compile large mixed-context inputs into a relevance-ranked, token-budgeted context packet with provenance and omission reasons. Use when an AI coding or research agent needs to select files, notes, logs, or retrieved passages before a task.
---

# Agent Context Compiler

## Workflow

1. Confirm the task boundary and identify whether the input contains secrets or personal data.
2. Normalize the input to the schema in `references/contract.md`.
3. Run `python scripts/run.py input.json --mode context`.
4. Treat validation failures as blockers; do not silently repair high-impact assumptions.
5. Return the machine-readable result plus a concise explanation of decisions and exclusions.

## Guardrails

- Never collect credentials, bypass access controls, evade rate limits, or expand tool permissions.
- Preserve provenance and distinguish observed facts from inferred conclusions.
- Require human review before high-impact external actions.
- Minimize retained data and redact unnecessary personal information.
- Keep outputs deterministic for identical normalized inputs.

## Resources

- Read `references/contract.md` for the input/output contract.
- Run `scripts/run.py` for deterministic execution.
