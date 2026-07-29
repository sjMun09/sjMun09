# Moonseongjun

**AI/AX Engineer — RAG · MCP · Data & Agent Systems**

I build AI systems that connect domain knowledge with operational data.
I came to AI through MES data, database migration, and backend systems, so I care as much about provenance, permissions, and failure modes as model output.

## Current Focus

- **Reliable RAG**\
  Retrieval evaluation, hybrid search, reranking, and failure analysis for domain documents.

- **Domain MCP**\
  Source-aware document tools and read-only business-data access with explicit approval boundaries.

- **Agent systems**\
  Terminal agents that can inspect, edit, and test code without hiding permissions or failure paths.

- **Data pipelines for AI**\
  Ingestion, normalization, metadata, versioning, and delivery from operational systems to AI applications.

## Open Source

- [MES Document MCP](https://github.com/sjMun09/MES-mcp)\
  An MCP server and CLI that turns Excel, PDF, Word, Markdown, and CSV files into source-traceable document data. Writes go through a proposed patch, dry run, approval, and validation.

- [Harness](https://github.com/sjMun09/Harness)\
  A Rust terminal coding agent with a read-edit-test loop and first-class support for legacy backend work involving XML, SQL, FreeMarker, and MyBatis.

## Engineering Principles

- Ground generated answers in inspectable sources.
- Measure retrieval changes on a fixed dataset before accepting them.
- Keep agent writes behind preview, approval, and validation.
- Treat observability, failure handling, and rollback as product behavior.

## Tech Stack

**AI / LLM**\
Python, FastAPI, RAG, MCP, pgvector, hybrid retrieval, reranking

**Data / Backend**\
Java, Spring Boot, MyBatis, PostgreSQL, Oracle, Liquibase, Redis, Elasticsearch

**Systems / Delivery**\
Rust, Docker, Jenkins, Ansible, OpenTelemetry, Grafana

## Writing & Contact

- TechLog: [sj-techlog.pages.dev](https://sj-techlog.pages.dev)
- Email: [ohoh7391@naver.com](mailto:ohoh7391@naver.com)
