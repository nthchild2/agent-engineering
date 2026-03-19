# Research Questions

## Question Backlog

1. What are generative AIs actually good at in agentic work?
   - Note: Excel at pattern recognition, code generation, and tool-mediated tasks (sources: OpenAI GPT-5.1, Anthropic Claude, survey paper).
2. What are they consistently bad at, even when they appear confident?
   - Note: Long-term memory, complex multi-step reasoning without external aids, reliable factual recall beyond training data, and non-deterministic outputs prone to hallucinations (Anthropic reduce hallucinations, OpenAI prompting guide).
3. Which operating parameters matter most in practice?
   - Note: Context window size, cost per token, latency, tool interfaces, and evaluation setups (Anthropic context, OpenAI models, MLE-bench).
4. What kinds of orchestration patterns make multiple agents stronger than one?
   - Note: Role separation, explicit handoffs, checkpoints for review, and tool-mediated execution (AutoGen, CrewAI, LangChain Agents).
5. Which human organizational patterns transfer well to AI agents, and which do not?
   - Note: Specialization and delegation transfer well; implicit communication and trust in confidence do not (Challenges in Human-Agent Communication, AutoGen).
6. How should agent orchestration change when the application domain is software engineering rather than general knowledge work?
   - Note: Emphasize executable feedback (tests, linters), artifact-centered workflows, and verification over self-confidence (SWE-bench, SWE-Agent, manifesto implications).
7. What is the unit of work for an agent: prompt, task, subtask, role, or accountable deliverable?
   - Note: Accountable deliverable or subtask with checkpoints, rather than loose prompts (AutoGen Studio, survey paper).
8. When should an agent be autonomous, and when should it be gated by a human?
   - Note: Autonomous for low-risk tasks with verification; gated for high-stakes or uncertain decisions (AutoGen, Challenges paper).
9. How should context be partitioned across agents so that more agents increase signal rather than noise?
   - Note: Assign specialized roles with partitioned context and external memory for shared state (Anthropic context, CrewAI).
10. What information should never live only in model context and must be externalized into tools, files, memory, or logs?
    - Note: Persistent state, shared artifacts, and audit trails must be externalized (Anthropic context, manifesto implications).
11. What is the right boundary between an agent and a tool?
    - Note: Agent proposes intent, tool executes; boundary at verifiable action vs. model reasoning (Anthropic tool use, OpenAI Assistants API).
12. How do we evaluate an orchestration design beyond anecdotal demos?
    - Note: Use benchmarks, real-world tasks, and executable validation (SWE-bench Verified, MLE-bench, GPT-5.1 for developers).
13. Which failures are model failures, which are orchestration failures, and which are specification failures?
    - Note: Model: hallucinations, determinism; Orchestration: poor handoffs, noise; Specification: unclear roles or goals (sources across buckets).
14. How do latency, cost, and reliability trade off against one another as we add more agents?
    - Note: More agents increase latency and cost but can improve reliability through specialization if designed well (AutoGen v0.4, operational constraints).
15. How should agents coordinate around shared artifacts such as code, tests, issues, plans, and architecture decisions?
    - Note: Use external artifacts for coordination, with logging and checkpoints (AutoGen Studio, SWE-Agent).
16. What is the minimum viable audit trail for trustworthy agentic software development?
    - Note: Logs of actions, verifications, and human overrides; traceable to sources and experiments (manifesto implications).
17. When does a multi-agent design outperform a single strong agent with good tools?
    - Note: When tasks require decomposition, specialization, and explicit roles; otherwise, single agent suffices (AutoGen, CrewAI).
18. What does "maximum capability" mean in practice: speed, quality, autonomy, throughput, or organizational leverage?
    - Note: Balance of quality, reliability, and leverage through orchestration, not just speed or autonomy (sources on trade-offs).

## Provisional Hypotheses

These are working theses to test during research. They are not yet validated conclusions.

- Most gains come from better decomposition, retrieval, tool use, and verification, not from adding more free-form conversation. (Validated: Supported by tool-mediated patterns and verification emphasis.)
- Multi-agent systems help most when roles, boundaries, and handoffs are explicit. (Validated: Matches orchestration patterns from AutoGen and CrewAI.)
- In software engineering, executable feedback from tests, type systems, linters, and runtime checks is more valuable than agent self-confidence. (Validated: Reinforced by SWE-bench and manifesto implications.)
- The scarcest resource is not tokens but trustworthy attention: what the system chooses to keep, surface, and verify. (Validated: Aligns with attention to verification and audit trails.)
- Agent orchestration should be designed around artifacts and checkpoints, not personalities. (Validated: Consistent with artifact-centered design in sources.)
