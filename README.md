# Awesome Agent Memory [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated, **auto-updating**, **vendor-neutral** list of frameworks, stores, benchmarks, and papers for **AI agent memory**, with benchmarks treated as a first-class category so you can tell what actually works.

An agent with no memory starts every conversation from zero. Memory is what lets it remember a user across sessions, learn from corrections, and not repeat itself. The field is split between academic paper-lists and vendor tool-lists; this one bridges them and pairs each production framework with the benchmarks behind it.

**Browse and filter: [agent-memory.agentpostmortem.com](https://agent-memory.agentpostmortem.com)**

## Start here: the mental model

**Types of memory.** Short-term / working (the context window) vs long-term (stored and recalled). Long-term splits into **episodic** (what happened), **semantic** (facts), and **procedural** (how to do things).

**Every memory system answers four questions:**
1. **What to remember** (everything, or a summarized profile).
2. **How to store it** (vector for similarity, graph for relationships, KV for facts, temporal for change over time).
3. **When to recall** (retrieval on every turn, or on demand via tools).
4. **When to forget** (decay, consolidation, or never).

**Then: does it work?** That is what the benchmarks section is for. LoCoMo and LongMemEval are the ones people actually cite.

**The one rule:** a memory system is only as good as its recall precision under real load. A store that returns the wrong three memories is worse than no memory at all.

<!-- LIST:START -->
**42 entries**, auto-refreshed weekly. Star counts updated **2026-08-03**. Browse the filterable version at **[agent-memory.agentpostmortem.com](https://agent-memory.agentpostmortem.com)**.

### Memory frameworks and libraries

- [Mem0](https://github.com/mem0ai/mem0) `* 62.4k`: Self-editing memory layer with user/session/agent scopes over a hybrid vector-plus-graph-plus-KV store; strong LoCoMo/LongMemEval scores.
- [Cognee](https://github.com/topoteretes/cognee) `* 29.7k`: Turns ingested data into a reasoning knowledge graph so memory improves from corrections; graph-first.
- [Graphiti](https://github.com/getzep/graphiti) `* 29.5k`: Zep's framework for building real-time, temporally-aware knowledge graphs for agent memory.
- [Letta (formerly MemGPT)](https://github.com/letta-ai/letta) `* 24.1k`: OS-inspired agent runtime where the agent self-manages tiered memory (main context as RAM, archival as disk) via memory tools and a REST API.
- [Memori](https://github.com/MemoriLabs/Memori) `* 15.7k`: LLM-agnostic, agent-native memory that turns agent execution into structured persistent state; enterprise/on-prem focus.
- [txtai](https://github.com/neuml/txtai) `* 12.8k`: All-in-one embeddings database for semantic search, LLM orchestration, and memory-style retrieval.
- [Zep](https://github.com/getzep/zep) `* 4.8k`: Memory server for agents built on a temporal knowledge graph that tracks fact-validity windows; strong on temporal queries.
- [MemoryScope](https://github.com/modelscope/MemoryScope) `* 3.3k`: ModelScope's long-term memory library for LLM chatbots with hierarchical, time-aware memory operations.
- [Memobase](https://github.com/memodb-io/memobase) `* 2.8k`: User-profile-based long-term memory for chatbot and agent apps with time-aware user event timelines.
- [Memary](https://github.com/kingjulio8238/Memary) `* 2.6k`: Open-source memory layer for autonomous agents that emulates how human memory evolves over time.
- [MemoRAG](https://github.com/qhjqhj00/MemoRAG) `* 2.3k`: RAG framework built on a long-memory model as a global data interface, targeting 1M-plus token tasks.
- [LangMem](https://github.com/langchain-ai/langmem) `* 1.6k`: LangChain's memory primitives for storing, recalling, and managing agent state within LangGraph workflows.
- [Memoripy](https://github.com/caspianmoon/memoripy) `* 693`: Python memory layer with short/long-term storage, semantic clustering, decay/reinforcement, and graph associations.
- [A-Mem](https://github.com/WujiangXu/A-mem-sys) `* 376`: Zettelkasten-inspired agentic memory that links structured knowledge notes for dynamic consolidation.
- [memonto](https://github.com/shihanwan/memonto) `* 99`: Ontology-driven memory library that structures agent memory around a user-defined schema.

### Framework-native memory

- [LangChain / LangGraph Memory](https://github.com/langchain-ai/langchain) `* 143.3k`: Widely used agent framework providing conversation buffers, summary memory, and state persistence/checkpointing.
- [LlamaIndex Memory](https://github.com/run-llama/llama_index) `* 51.3k`: Data framework with built-in chat memory buffers, vector memory, and composable memory modules for agents.
- [GraphRAG (Microsoft)](https://github.com/microsoft/graphrag) `* 35.2k`: Graph-based RAG that builds a knowledge graph from documents for structured, memory-like retrieval.
- [Haystack](https://github.com/deepset-ai/haystack) `* 26.1k`: Production LLM/RAG framework with memory and retrieval components for agent pipelines.

### Vector and graph memory stores

- [Milvus](https://github.com/milvus-io/milvus) `* 45.5k`: Scalable open-source vector database for storing and retrieving embedding-based memories.
- [FAISS](https://github.com/facebookresearch/faiss) `* 40.7k`: Library for efficient similarity search over dense vectors, a common low-level memory index.
- [Qdrant](https://github.com/qdrant/qdrant) `* 33.8k`: High-performance open-source vector database commonly used as the embedding store for agent long-term memory.
- [Chroma](https://github.com/chroma-core/chroma) `* 28.9k`: Developer-friendly embedded vector database popular for prototyping agent memory.
- [Neo4j](https://github.com/neo4j/neo4j) `* 17k`: Leading graph database used for knowledge-graph and relational agent memory.
- [Weaviate](https://github.com/weaviate/weaviate) `* 16.7k`: Open-source vector database with hybrid search, frequently backing semantic agent memory.
- [FalkorDB](https://github.com/FalkorDB/FalkorDB) `* 4.9k`: Low-latency graph database designed for GraphRAG and agent knowledge-graph memory.

### Benchmarks and evals

- [LoCoMo](https://github.com/snap-research/locomo) `* 1.1k`: Very long-term conversational memory benchmark; 1,540 questions across single-hop, multi-hop, temporal, open-domain.
- [LongMemEval](https://github.com/xiaowu0162/LongMemEval) `* 976`: 500-question benchmark for chat-assistant long-term interactive memory across six abilities.
- [agentos-bench (BEAM)](https://github.com/framerslab/agentos-bench) `* 0`: Benchmark harness bundling LongMemEval, LoCoMo, BEAM, plus cognitive-mechanism micro-benchmarks.
- [Mem0 State-of-AI-Memory report](https://mem0.ai/blog/state-of-ai-agent-memory-2026): Comparative benchmark report scoring memory systems on LoCoMo, LongMemEval, and BEAM with token-cost analysis.

### Papers and surveys

- [Awesome-Memory-for-Agents (papers)](https://github.com/TsinghuaC3I/Awesome-Memory-for-Agents) `* 624`: Curated academic collection of papers on memory for language agents.
- [MemGPT paper](https://arxiv.org/abs/2310.08560): 'MemGPT: Towards LLMs as Operating Systems', the tiered virtual-context memory idea behind Letta.
- [LoCoMo paper](https://arxiv.org/abs/2402.17753): 'Evaluating Very Long-Term Conversational Memory of LLM Agents', a foundational conversational-memory benchmark.
- [LongMemEval paper](https://arxiv.org/abs/2410.10813): 'Benchmarking Chat Assistants on Long-Term Interactive Memory'.

### Managed memory services

- [Mem0 Platform](https://mem0.ai/): Hosted managed memory API and platform (graph features gated behind a paid tier).
- [Zep Cloud](https://www.getzep.com/): Managed temporal-knowledge-graph memory service for agents and assistants.
- [Letta Cloud](https://www.letta.com/): Hosted platform for building and running stateful, self-managing memory agents.
- [Cognee Cloud](https://www.cognee.ai/): Managed offering of the Cognee knowledge-graph memory engine.
- [Graphlit](https://graphlit.com/): Managed knowledge/memory API turning content into a searchable graph for agents.
- [Ragie](https://ragie.ai/): Managed RAG and retrieval-memory-as-a-service for agent applications.

### Learning resources

- [HybridAGI](https://github.com/SynaLinks/HybridAGI) `* 905`: Neuro-symbolic agent system combining graph-program memory with LLMs.
- [Agent Memory Techniques (notebooks)](https://github.com/NirDiamant/Agent_Memory_Techniques) `* 833`: 30 runnable notebooks: buffers, vector stores, KGs, episodic/semantic memory, MemGPT, Mem0, Letta, Zep, Graphiti, LoCoMo.

<!-- LIST:END -->

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Edit `data/tools.json`, run `node scripts/generate.mjs`, open a PR.

## License

[CC0 1.0](LICENSE) (public domain).
