---
name: neuralese
description: Reduce token use on reasoning and agent tasks by using compact, task-specific representations when they preserve meaning and improve success. Applies to deliberate token-efficiency requests and long multi-step workflows; it cannot directly control a model's hidden activations.
---

# Neuralese

Use the smallest representation that keeps the task solvable. “Neuralese” here means compact machine-usable state (for example, a schema, symbols with a legend, IDs, equations, or a terse checklist), not literal access to hidden states or a new language the model is presumed to understand.

## Method

- First identify what information must survive: goal, constraints, inputs, decisions, evidence, and uncertainty. Keep exact values and distinctions that could change the result.
- Prefer established compact forms suited to the task: tables/JSON for records, equations for quantitative relations, short labels plus a legend for repeated concepts, and checklists for execution state. Reuse labels consistently.
- Compress repeated or already-known context; preserve exceptions, dependencies, provenance, and unresolved questions. For handoffs, provide only the minimal sufficient state and the next action.
- Do not invent an opaque code when ordinary concise language or a standard structure is clearer. Define any shorthand once, then verify it preserves the intended meaning.
- Spend tokens where they prevent errors: ambiguity checks, calculations, source verification, safety-critical constraints, and validation. If compression increases uncertainty or likely retries, use clearer language; optimize total effort, not prompt length alone.
- Keep user-facing answers readable and include enough reasoning/evidence to make consequential conclusions checkable. Do not expose a cryptic intermediate representation as the final answer unless requested.

## Limits

Prompting can change visible text and task organization; it does not give the assistant direct access to continuous hidden-state communication or guarantee fewer model-internal reasoning tokens. Follow the model and tool interface actually available. Never claim a token or quality improvement without measurement. For repeated workflows, compare compact and ordinary forms on representative tasks using the same success criteria and include retries and output quality in the cost.
