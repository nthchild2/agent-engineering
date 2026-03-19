# Agent Engineering

`agent-engineering` is a research and development repository for agentic AI methodology, using software development as an early proving ground.

## Main Goal

Develop a formal methodology for orchestrating agentic AI at maximum practical capability, then turn that methodology into concrete tools, workflows, and evaluation methods.

## Why This Exists

It is no longer enough to ask whether AI can assist real work. It already does. The harder question is how to organize models, tools, memory, evaluation, and human judgment so the overall system produces better outcomes than either a lone human or an unstructured chat loop.

This repository exists to answer that question seriously.

## Current Direction

The work proceeds in two stages:

1. Write a general manifesto on agentic orchestration.
2. Validate it in software development and derive tools from it rather than inventing tools first and rationalizing them later.

## Working Principles

- Start from first principles and operational constraints.
- Separate what is true from what is aspirational.
- Prefer source-backed claims, experiments, and executable feedback over intuition alone.
- Treat orchestration as a systems design problem, not a prompt-writing trick.
- Build around artifacts, checkpoints, and verification.
- Iterate on repository instructions as the methodology hardens.

## Repository Structure

- `README.md`: repository purpose, direction, and durable framing.
- `AGENTS.md`: repository rules for coding agents.
- `.github/copilot-instructions.md`: aligned instructions for AI-assisted development tools.
- `research/`: temporary research notes, source collection, and exploratory thinking.
- `plans/`: documented plans for repository development and process steps.

## Where To Resume

Use `README.md` as the durable entry point and `research/` as the working area.

- `README.md`: the main goal, current direction, and the durable framing of the repository.
- `research/`: provisional work such as open questions, sources, early theses, and draft postulates.
- `research/questions.md`: the active question backlog.
- `research/sources.md`: the auditable source list.
- Next durable progress file to add: `research/status.md` as a session handoff and resume point.

## Near-Term Questions

- What are generative models good at in agentic work?
- What are they bad at or unreliable at?
- Which operating parameters matter most in practice?
- When does multi-agent orchestration outperform a single strong agent?
- Which orchestration patterns actually hold up in real work?
- What should be measured to judge whether an agentic workflow is any good?

## Contribution Standard

Contributions should tighten the methodology, improve the clarity of the repository’s purpose, or advance a concrete tool or workflow that follows from the emerging manifesto.
