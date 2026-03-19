# AGENTS.md

This file defines repository-level guidance for coding agents working in this project.

## Scope
- Applies to the entire repository unless a deeper `AGENTS.md` overrides it.

## Repository Purpose
- This repository exists to develop a formal methodology for integrating agentic AI into software development at maximum practical capability.
- The work starts with a manifesto on agentic orchestration and then turns those postulates into tools, workflows, and evaluation methods.
- Treat the repository as a research-and-build environment, not a generic app scaffold.

## Main Goal
- Help define, test, and operationalize a rigorous approach to agentic software development.
- Prefer work that improves one of these three outcomes:
- clearer principles
- stronger orchestration patterns
- more reliable developer tooling

## Working Mode
- Favor explicit reasoning over hand-wavy claims.
- Separate descriptive claims from normative claims:
- descriptive: how models, tools, and agents actually behave
- normative: how this repository says they should be used
- Ground important claims in sources, experiments, or executable evidence.
- Keep changes small, legible, and easy to revise as the methodology evolves.

## Repository Priorities
- `README.md` is the primary statement of purpose, scope, and current direction.
- `AGENTS.md` defines how coding agents should behave in this repository.
- `.github/copilot-instructions.md` should align with the repository purpose and reinforce the same operating model for AI assistance.
- `research/` is a temporary workspace for gathering questions, sources, notes, and early theses before material is promoted into durable docs or tools.

## Documentation Rules
- When changing the intended workflow, update the relevant documentation in the same task.
- Prefer concise, opinionated writing over generic AI platitudes.
- Make it easy to trace a claim back to one of the following:
- a source
- an experiment
- a benchmark
- a repository decision
- If a concept is provisional, label it as provisional.

## Engineering Rules
- Build tools only after the motivating principle or problem is written down clearly.
- Prefer artifact-centered workflows over chat-centered workflows.
- Design for verification, auditability, and reversibility.
- Avoid adding framework-like complexity before it is justified by a concrete orchestration need.
- Preserve existing structure and naming unless there is a strong reason to change them.

## Validation
- Before finishing code or documentation changes, run the smallest relevant validation available.
- Prefer targeted checks over broad ones.
- If no automated validation exists for the change, say so explicitly.

## Git Hygiene
- Do not revert user changes outside the requested task.
- Keep diffs focused and avoid unrelated refactors.
- Do not commit, amend, or create branches unless the user asks.

## Handoff
- In final updates, summarize what changed, note any validation performed, and call out open questions or remaining uncertainties.
