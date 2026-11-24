# Munseongjun (문성준)

**Backend Engineer** · Java · Spring Boot · PostgreSQL

I build backend systems, add AI where it actually earns its place, and run them in production myself.
My background is backend development and database work, so I care as much about data provenance, permissions, and failure modes as about features.

---

## What I Do

### Backend — core

- Domain modeling and REST API design with **Java / Spring Boot**, MyBatis and JPA side by side.
- Schema design, query tuning, and versioned migrations on **PostgreSQL** and **Oracle** (Liquibase).
- Caching and search as part of the data layer: **Redis**, **Elasticsearch**.
- Production service ownership, not just feature delivery — see [nomuhero.com](https://nomuhero.com).

### AI / AX

- **Reliable RAG** — retrieval evaluation, hybrid search, reranking, and failure analysis on domain documents. Retrieval changes get measured on a fixed dataset before they ship.
- **MCP servers** — source-aware document tools and read-only business-data access with explicit approval boundaries.
- **Agent systems** — terminal agents that inspect, edit, and test code without hiding permissions or failure paths.
- **Data pipelines for AI** — ingestion, normalization, metadata, versioning, and delivery from operational systems into AI applications.

### Infrastructure & Operations

- Containerized delivery with **Docker**, CI/CD pipelines on **Jenkins**, provisioning with **Ansible**.
- Observability as product behavior: **Prometheus**, **Grafana**, **OpenTelemetry**.
- PostgreSQL operations — version upgrades, container-to-native migration, backup and recovery.
- Running my own service on **NCP**: deployment, domain and TLS, monitoring, incident recovery.

---

## Selected Work

| Project | What it is | Stack |
|---|---|---|
| 노무히어로 ([nomuhero.com](https://nomuhero.com)) | Attendance, payroll, and employee management SaaS for small businesses. Built and operated end to end — 600+ commits, live in production. *(private repo)* | Java, Spring Boot, PostgreSQL, NCP |
| Gout Care | Community platform for gout patients — emergency guides, diet, uric-acid logs, hospital search. Monorepo with a Spring Boot API, a Next.js PWA, and a local inference service; runs natively on a single host with daily `pg_dump` backups and GitHub Actions CI/CD. *(private repo)* | Java 21, Spring Boot, QueryDSL, PostgreSQL 17 + PostGIS + pgvector, Redis, Flyway |
| [Harness](https://github.com/sjMun09/Harness) | Terminal coding-agent CLI with a read–edit–test loop and first-class support for legacy backend refactoring (XML, SQL, FreeMarker, MyBatis). | Rust |

---

## Engineering Principles

- Ground generated answers in inspectable sources.
- Measure retrieval and performance changes on a fixed dataset before accepting them.
- Keep agent and automated writes behind preview, approval, and validation.
- Treat observability, failure handling, and rollback as product behavior, not ops afterthoughts.

---

## Tech Stack

| Area | Tools |
|---|---|
| **Languages** | Java, Python, TypeScript, Rust, SQL |
| **Backend** | Spring Boot, JPA, QueryDSL, MyBatis, Spring Security, FastAPI, Next.js |
| **Data** | PostgreSQL, Oracle, Redis, Elasticsearch, Flyway, Liquibase, pgvector, PostGIS |
| **AI / LLM** | RAG, hybrid retrieval, reranking, MCP, Anthropic SDK |
| **Infra** | Docker, Jenkins, Ansible, Prometheus, Grafana, OpenTelemetry, NCP |

---

## Writing & Contact

- TechLog — [sj-techlog.pages.dev](https://sj-techlog.pages.dev)
- Email — [ohoh7391@naver.com](mailto:ohoh7391@naver.com)
