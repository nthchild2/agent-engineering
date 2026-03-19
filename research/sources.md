- OpenAI GPT-5.1 model page
  - URL: https://platform.openai.com/docs/models/gpt-5.1
  - Why it matters: gives an official snapshot of coding/agentic positioning, context window, output limits, reasoning-effort control, and knowledge cutoff.
- OpenAI GPT-4.1 model page
  - URL: https://platform.openai.com/docs/models/gpt-4.1
  - Why it matters: useful contrast case for large context without an explicit reasoning step.
- OpenAI prompting guide: strategies to improve reliability
  - URL: https://platform.openai.com/docs/guides/prompt-engineering/strategies-to-improve-reliability
  - Why it matters: explicitly frames outputs as non-deterministic and recommends snapshot pinning and evals.
- Anthropic context windows
  - URL: https://docs.anthropic.com/en/docs/build-with-claude/context-windows
  - Why it matters: strong explanation of context as working memory, token accounting, tool-use interaction, and context overflow behavior.
- Anthropic tool use overview
  - URL: https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview
  - Why it matters: shows the actual control loop for tool-mediated work and clarifies the boundary between model intent and external execution.
- Anthropic reduce hallucinations
  - URL: https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/reduce-hallucinations
  - Why it matters: official guidance on uncertainty, grounding, verification, and iterative checking.
- AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation
  - URL: https://www.microsoft.com/en-us/research/publication/autogen-enabling-next-gen-llm-applications-via-multi-agent-conversation-framework/
  - Why it matters: foundational paper for composing multiple conversable agents with tools and optional human input.
- AutoGen v0.4: actor-model redesign
  - URL: https://www.microsoft.com/en-us/research/articles/autogen-v0-4-reimagining-the-foundation-of-agentic-ai-for-scale-extensibility-and-robustness/
  - Why it matters: suggests that robustness and scale require stronger execution models than informal chat loops.
- AutoGen Studio: A No-Code Developer Tool for Building and Debugging Multi-Agent Systems
  - URL: https://www.microsoft.com/en-us/research/publication/autogen-studio-a-no-code-developer-tool-for-building-and-debugging-multi-agent-systems/
  - Why it matters: highlights workflow specification, debugging, and evaluation as first-class needs, not afterthoughts.
- Challenges in Human-Agent Communication
  - URL: https://doi.org/10.48550/arXiv.2412.10380
  - Why it matters: points toward a core manifesto issue: human-agent coordination is itself a design problem.
- SWE-bench Verified
  - URL: https://openai.com/index/introducing-swe-bench-verified/
  - Why it matters: explains why benchmark quality matters and why naive measurements can misstate software-engineering capability.
- SWE-Lancer benchmark
  - URL: https://openai.com/index/swe-lancer/
  - Why it matters: grounds the discussion in real freelance software tasks and shows frontier models still miss most tasks.
- MLE-bench
  - URL: https://openai.com/index/mle-bench/
  - Why it matters: useful adjacent evidence that agent performance depends heavily on scaffolding, evaluation setup, and available tools.
- GPT-5.1 for developers
  - URL: https://openai.com/index/gpt-5-1-for-developers/
  - Why it matters: provides recent coding and agentic benchmark results and reinforces the importance of tool-enabled evaluation.
- Anthropic Claude 3.5 Sonnet model page
  - URL: https://docs.anthropic.com/en/docs/about-claude/models#model-comparison
  - Why it matters: details on latest Claude capabilities for coding, tool use, and agentic tasks.
- xAI Grok model documentation
  - URL: https://docs.x.ai/docs/models
  - Why it matters: alternative model with real-time search, coding abilities, and agentic positioning.
- LangChain Agents documentation
  - URL: https://python.langchain.com/docs/modules/agents/
  - Why it matters: popular framework for building agentic workflows with tools and memory.
- CrewAI documentation
  - URL: https://docs.crewai.com/
  - Why it matters: multi-agent orchestration framework with roles and handoffs.
- SWE-Agent repository
  - URL: https://github.com/princeton-nlp/SWE-agent
  - Why it matters: open-source agent for software engineering tasks, demonstrating practical agent design.
- A Survey on Large Language Model based Autonomous Agents
  - URL: https://arxiv.org/abs/2308.11421
  - Why it matters: comprehensive survey on agent architectures, capabilities, and limitations.
- GitHub Copilot documentation
  - URL: https://docs.github.com/en/copilot
  - Why it matters: real-world agentic tool in development environments, showing integration patterns.
- OpenAI Assistants API
  - URL: https://platform.openai.com/docs/assistants/overview
  - Why it matters: official API for building agentic applications with tools and conversation management.
Use four buckets when extracting notes from sources:
1. Descriptive truths
   - Claims about how models and agents behave.
2. Operational constraints
   - Context, cost, latency, tool interfaces, memory, determinism, and evaluation limits.
3. Orchestration design patterns
   - Delegation, review, verification, memory, role separation, and human override.
4. Manifesto implications
   - Normative statements that should become postulates.

## Extracted Notes

### Descriptive Truths
- Generative models excel at pattern recognition, code generation, and tool-mediated tasks but struggle with long-term memory, complex multi-step reasoning without external aids, and reliable factual recall beyond training data (e.g., OpenAI GPT-5.1, Anthropic Claude, xAI Grok).
- Agents built on LLMs are non-deterministic, prone to hallucinations, and require iterative verification; confidence scores do not correlate strongly with accuracy (Anthropic reduce hallucinations, OpenAI prompting guide).
- Multi-agent systems can outperform single agents in decomposition and specialization but introduce coordination overhead and noise if roles are not explicit (AutoGen papers, CrewAI, LangChain Agents).
- In software engineering, agents perform well on isolated tasks like code completion or bug fixes but fail on end-to-end workflows without proper scaffolding, tools, and evaluation (SWE-bench, SWE-Lancer, SWE-Agent, MLE-bench).
- Human-agent communication is a bottleneck, with agents often misinterpreting intent or over-relying on implicit context (Challenges in Human-Agent Communication).
- Real-time capabilities (e.g., search integration) enhance agent utility but add latency and cost (xAI Grok, GitHub Copilot).

### Operational Constraints
- Context windows range from 4K to 128K+ tokens, limiting working memory; overflow leads to truncation or summarization (Anthropic context windows, OpenAI models).
- Costs scale with token usage, reasoning effort, and tool calls; latency increases with model size and multi-agent interactions (OpenAI pricing, GPT-5.1 for developers).
- Tool interfaces vary by provider, requiring adaptation; determinism is low without snapshot pinning or evals (Anthropic tool use, OpenAI Assistants API).
- Memory must be externalized (files, databases) as models lack persistent state; evaluation benchmarks often overstate capabilities due to controlled setups (MLE-bench, SWE-bench Verified).
- Agent frameworks impose overhead for orchestration, debugging, and scaling (AutoGen Studio, CrewAI).

### Orchestration Design Patterns
- Role separation and handoffs: Assign specialized roles to agents, with explicit checkpoints for review (AutoGen, CrewAI).
- Tool-mediated execution: Models propose actions, tools execute, with feedback loops for verification (Anthropic tool use, LangChain Agents).
- Human override and gating: Include human judgment for high-stakes decisions or when uncertainty is high (AutoGen, Challenges in Human-Agent Communication).
- Memory and context management: Partition context across agents, use external artifacts for shared state (Anthropic context, survey paper).
- Debugging and evaluation: Build workflows with logging, testing, and benchmark validation (AutoGen Studio, SWE-Agent).

### Manifesto Implications
- Prioritize tool-enabled agents over raw model outputs to ground responses in verifiable actions.
- Design orchestration around artifacts (code, tests, docs) rather than conversational loops for auditability.
- Validate agent outputs through executable feedback (tests, linters) before trusting them in workflows.
- Use multi-agent patterns only when roles and boundaries are clear, avoiding over-complication.
- Treat human coordination as a core design problem, not an afterthought.
- Measure success via real-world tasks and benchmarks, not anecdotal demos.
