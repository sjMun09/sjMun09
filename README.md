# Moonseongjun / 문성준

### AI/AX Backend Engineer | LLM Application · RAG · MCP

I build AI applications that connect domain documents and live business data.
My background is DBA and MES backend development, so I care about the data model, source provenance, evaluation, permissions, and operational boundaries behind an LLM response.

## Current Focus

- **RAG evaluation and retrieval quality**
  Built a 50-question MES golden-set harness with Hit@5, MRR, RAGAS, and latency tracking. In a controlled dense-only vs. hybrid comparison, Hit@5 moved from `0.220` to `0.660`, while latency increased from `9.624s` to `12.728s`. This is a retrieval result, not a generic answer-accuracy claim.

- **MES RAG + MCP applications**
  Separated document-grounded questions from live MES queries. Implemented natural-language access for material issue, net demand, work order, process inspection, inventory, and closing domains, including dynamic date parameters, multi-domain calls, and related-screen navigation.

- **Reliable LLM application paths**
  Worked on document-aware chunking, content-hash deduplication, embedding-space isolation, semantic cache, reranker fallback, stage-level latency diagnostics, and prevention of provider-error text entering the knowledge base.

- **Data and delivery foundations**
  Experience with PostgreSQL, Oracle, Liquibase, Spring Boot/MyBatis, Jenkins, Ansible, Docker, Grafana, and OpenTelemetry. I use these foundations to make AI workflows reviewable and repeatable.

## Selected Work

| Area | What I worked on |
| --- | --- |
| MES RAG Evaluation | Implemented an evaluation harness and expanded an MES golden set to 50 questions. Compared retrieval paths with Hit@5, MRR, RAGAS, and latency instead of relying on subjective chat quality. |
| RAG Pipeline | Built document ingestion and retrieval improvements: structure-preserving chunking, duplicate prevention, multi-embedding isolation, reranker fallback, and failure-path diagnostics. |
| MES MCP | Extended seven MES data-query areas and orchestrated multi-domain tool calls with dynamic date/closing-month parameters. |
| MES Backend / DB | Implemented dynamic planning SQL with Spring Boot, MyBatis, and FreeMarker. Contributed to Liquibase multi-tenant structure and PostgreSQL migration work. |
| Delivery / Observability | Implemented Backend deployment role/playbooks and contributed to CI/CD, runtime configuration, Grafana, OpenTelemetry, Loki, Tempo, and alert improvements. |

## Public Project

- **[MES Document MCP](https://github.com/sjMun09/MES-mcp)**
  A guarded MCP server for Excel, PDF, Word, Markdown, and CSV documents used in MES workflows. It preserves source provenance through `DocumentIR`, proposes changes through `PatchIR`, requires dry-run and approval before writes, and validates exported artifacts.
  I used AI coding agents while personally defining the requirements, safety policy, test criteria, and release validation.

## Tech Stack

**LLM Application**
Python, FastAPI, RAG, MCP, RAGAS, pgvector, hybrid retrieval, reranking, embedding, SSE

**Backend / Database**
Java, Spring Boot, MyBatis, FreeMarker, PostgreSQL, Oracle, Liquibase, SQL

**Delivery / Observability**
Docker, Jenkins, Ansible, Linux, Grafana, OpenTelemetry, Loki, Tempo, Mimir

## Writing

- TechLog: [sj-techlog.pages.dev](https://sj-techlog.pages.dev)
- GitHub: [github.com/sjMun09](https://github.com/sjMun09)

## Contact

- Email: [ohoh7391@naver.com](mailto:ohoh7391@naver.com)
