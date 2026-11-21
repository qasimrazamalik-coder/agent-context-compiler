# Contract

## Purpose
Agents waste tokens by loading context in discovery order instead of value order.

## Input
JSON containing task, token_budget, and items with id, text, relevance, freshness, trust and required flags.

## Output
A deterministic context manifest with selected items, token estimate, provenance and excluded-item reasons.

## Failure behavior
Reject malformed JSON. Report missing or unsafe fields explicitly. Never invent evidence or authorization.
