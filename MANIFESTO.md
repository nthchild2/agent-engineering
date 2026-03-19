# Manifesto for Agentic Orchestration

This manifesto outlines postulates for orchestrating agentic AI at maximum practical capability, grounded in source-backed research. It separates descriptive claims (how agents behave) from normative claims (how they should be used). Postulates are derived from validated hypotheses and extracted notes in `research/sources.md` and `research/questions.md`.

## Descriptive Claims
These describe observed behaviors of models and agents, based on empirical evidence.

1. **Non-Determinism and Hallucinations**: Generative models produce non-deterministic outputs prone to hallucinations; confidence does not reliably indicate accuracy (Anthropic reduce hallucinations, OpenAI prompting guide).
2. **Strengths in Pattern Tasks**: Models excel at pattern recognition, code generation, and tool-mediated execution but struggle with long-term memory and complex reasoning without aids (OpenAI GPT-5.1, survey paper).
3. **Operational Limits**: Context windows, costs, latency, and tool interfaces constrain agent performance; memory must be externalized (Anthropic context, operational constraints).
4. **Multi-Agent Dynamics**: Multiple agents improve outcomes through specialization but add coordination overhead if roles are unclear (AutoGen, CrewAI).
5. **Domain-Specific Challenges**: In software engineering, agents require executable feedback for reliability, as self-confidence is insufficient (SWE-bench, SWE-Agent).

## Normative Postulates
These prescribe how to design and use agentic systems for better outcomes.

1. **Tool-Enable Agents**: Always equip agents with tools for verifiable execution; avoid relying on raw model outputs alone (Anthropic tool use, validated hypothesis 1).
2. **Artifact-Centered Orchestration**: Design workflows around shared artifacts (code, tests, docs) with checkpoints and logs, not conversational personalities (AutoGen Studio, validated hypothesis 5).
3. **Prioritize Verification**: Validate agent outputs through executable feedback (tests, linters) before integration; treat self-confidence as unreliable (SWE-bench, validated hypothesis 3).
4. **Explicit Roles and Handoffs**: Use multi-agent patterns only with clear roles, boundaries, and handoffs to avoid noise (CrewAI, validated hypothesis 2).
5. **Human Coordination as Design**: Treat human-agent communication as a core problem; gate autonomy for high-stakes decisions (Challenges paper, question 8).
6. **Externalize Critical Information**: Never store persistent state, audit trails, or shared knowledge solely in model context; use files, databases, or logs (Anthropic context, question 10).
7. **Evaluate Rigorously**: Measure orchestration via benchmarks and real tasks, not demos; distinguish model, orchestration, and specification failures (SWE-bench Verified, question 12).
8. **Balance Trade-Offs**: Optimize for quality and reliability over speed or autonomy when adding agents; consider latency and cost (AutoGen v0.4, question 14).
9. **Focus on Attention**: The scarcest resource is trustworthy attention; design systems to surface and verify key information efficiently (validated hypothesis 4).
10. **Domain Adaptation**: In software engineering, emphasize decomposition, retrieval, and verification over general conversation (SWE-Agent, question 6).
