# Application Projects

Practical software that makes infrastructure and network operations easier to run.

## What I build
- **Python tooling & CLIs** — provisioning, monitoring, and reporting utilities for the network and
  virtualization estate.
- **Vendor-API integrations** — pulling and correlating data from network and platform REST APIs.
- **Retrieval over operational knowledge** — a local **semantic-search / RAG** service over my own
  runbooks and notes (embeddings + vector search), so answers come from real context.

## Best practices I follow
- **Small, composable, dependable** — Unix-y tools that do one thing, scriptable and cron-safe.
- **Ground the model in real data** — for RAG: sane chunking, good embeddings, a vector store,
  and evaluation; never let an LLM freelance over infrastructure.
- **Read-only by default for ops tooling** — observe and report before anything mutates.
- **Secrets and state handled explicitly** — no creds in code, deterministic outputs.

## Where the field went (dated)
- **2023–2024:** **RAG** moves from novelty to standard practice — embeddings + vector search
  (FAISS, vector databases) grounding LLM answers in your own data.
- **2024–2025:** **LLM-assisted AIOps** becomes real — incident triage, root-cause analysis, and
  log-anomaly detection (e.g. RAG-over-logs) built on retrieval over runbooks and telemetry.

My tooling sits at that intersection: small, reliable automation that increasingly uses
retrieval/LLM techniques to make operational knowledge searchable and actionable.
