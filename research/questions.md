# Research Questions

## Question Backlog

1. What are generative AIs actually good at in agentic work?
2. What are they consistently bad at, even when they appear confident?
3. Which operating parameters matter most in practice?
4. What kinds of orchestration patterns make multiple agents stronger than one?
5. Which human organizational patterns transfer well to AI agents, and which do not?
6. How should agent orchestration change when the application domain is software engineering rather than general knowledge work?
7. What is the unit of work for an agent: prompt, task, subtask, role, or accountable deliverable?
8. When should an agent be autonomous, and when should it be gated by a human?
9. How should context be partitioned across agents so that more agents increase signal rather than noise?
10. What information should never live only in model context and must be externalized into tools, files, memory, or logs?
11. What is the right boundary between an agent and a tool?
12. How do we evaluate an orchestration design beyond anecdotal demos?
13. Which failures are model failures, which are orchestration failures, and which are specification failures?
14. How do latency, cost, and reliability trade off against one another as we add more agents?
15. How should agents coordinate around shared artifacts such as code, tests, issues, plans, and architecture decisions?
16. What is the minimum viable audit trail for trustworthy agentic software development?
17. When does a multi-agent design outperform a single strong agent with good tools?
18. What does "maximum capability" mean in practice: speed, quality, autonomy, throughput, or organizational leverage?

## Provisional Hypotheses

These are working theses to test during research. They are not yet validated conclusions.

- Most gains come from better decomposition, retrieval, tool use, and verification, not from adding more free-form conversation.
- Multi-agent systems help most when roles, boundaries, and handoffs are explicit.
- In software engineering, executable feedback from tests, type systems, linters, and runtime checks is more valuable than agent self-confidence.
- The scarcest resource is not tokens but trustworthy attention: what the system chooses to keep, surface, and verify.
- Agent orchestration should be designed around artifacts and checkpoints, not personalities.
