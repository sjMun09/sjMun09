# 문성준 | Moonseongjun

### AI/AX Backend Engineer with DBA · MES Data Experience

`LLM Application` `RAG` `MCP` `MES Data` `Backend / DBA`

Oracle→PostgreSQL 전환과 MES 업무 SQL에서 시작해, 문서와 실시간 생산 데이터를 RAG·MCP로 연결했습니다. 검색 평가부터 실패 처리·배포·DB 관측까지 구현합니다.

[![TechLog](https://img.shields.io/badge/TechLog-sj--techlog.pages.dev-2563EB?style=flat-square)](https://sj-techlog.pages.dev)
[![MES Document MCP](https://img.shields.io/badge/GitHub-MES%20Document%20MCP-181717?style=flat-square&logo=github)](https://github.com/sjMun09/MES-mcp)
[![Email](https://img.shields.io/badge/Email-ohoh7391%40naver.com-03C75A?style=flat-square)](mailto:ohoh7391@naver.com)

## About

공식 직무는 DBA였습니다. Oracle 기반 MES를 PostgreSQL로 전환하는 팀 작업에 참여했고, Liquibase 변경 관리, 멀티테넌트 스키마, 업무 SQL과 백업·복구 전략을 다뤘습니다. 이 과정에서 익힌 데이터 구조와 프로시저를 RAG 지식문서와 MCP 조회 도구의 기준으로 사용했습니다.

AI로 방향을 바꾸면서 DBA 경험을 버린 것이 아닙니다. DB 변경의 재현성, 테넌트 경계, 데이터 정합성, 복구 가능성을 LLM application에도 그대로 적용했습니다. 문서에서 찾을 절차·업무 규칙은 RAG로, 현재 재고·작업·품질·마감 상태는 read-only MCP로 분리합니다.

**지원 방향**: LLM Application Engineer · AI/AX Backend Engineer · 제조 AI Solution Engineer

## Numbers

| MES 지식문서 | 평가 골든셋 | 검색 Hit@5 | MCP 조회 영역 |
| :---: | :---: | :---: | :---: |
| **51건** | **50문항** | **0.220 → 0.660** | **7개** |
| 화면·코드·SQL·프로시저·가이드 대조 | 동일 조건 A/B 평가 | dense-only 대비 hybrid | MES 실시간 업무 조회 |

`0.220 → 0.660`은 일반 정답률이 아닙니다. 동일 MES 50문항에서 관련 문서가 Top 5 안에 회수된 비율입니다. MRR은 `0.220 → 0.439`, 평균 지연시간은 `9.624s → 12.728s`였습니다. 팀이 구현한 BM25+vector 검색을 제가 만든 평가 하네스·골든셋으로 검증했습니다.

## Experience

### 런업컴퍼니 · DynaMOS 제조 MES 플랫폼

**DBA · 2025.11 - 2026.08.21 종료 예정**

- **Oracle→PostgreSQL 전환**: 팀 전환 작업에 참여했습니다. Liquibase 멀티테넌트 구조, 환경별 schema hardcoding·checksum 문제, 설정·감사 스키마 changeset을 담당했습니다.
- **DB 변경 관리**: 테이블·제약조건·함수·프로시저·뷰의 의존 순서와 changelog 구성을 다루고, dev·qa·main에서 같은 변경을 재현할 수 있도록 schema prefix와 include 순서를 점검했습니다.
- **백업·복구 전략**: 현재 규모에는 pg_dump가 적합하다고 판단하고 DB 단위 복구와 검증 절차를 문서화했습니다. WAL/PITR과 pgBackRest는 단계적 도입 방향을 검토했으며 구축 완료 성과로 표기하지 않습니다.
- **RAG 평가 체계**: MES 50문항 골든셋과 Hit@5, MRR, RAGAS, latency 평가 하네스를 구현했습니다. 실제 서비스의 RAG 처리 함수를 호출해 offline 평가와 서비스 경로 차이를 줄였습니다.
- **AI 데이터 파이프라인**: 18개 MES 화면의 프론트 코드, MyBatis SQL, 프로시저, 테이블과 사용자 가이드를 대조해 지식문서 51건을 구성했습니다. 필수값·기본값·필터 조건 불일치 22건을 식별하고 교정했습니다.
- **RAG 신뢰성**: 표·코드 블록을 보호하는 청킹, content hash 중복 차단, 임베딩 모델별 벡터 공간 격리, semantic cache, reranker fallback과 단계별 latency 진단을 구현했습니다.
- **MES MCP**: 원자재불출, 순수요계획, 작업지시, 공정검사, 재고·마감 등 7개 조회 영역을 연결했습니다. 날짜·마감월 파라미터 해석, 다중 도메인 병렬 호출, 관련 MES 화면 이동을 구현했습니다.
- **외부 고객사 AI PoC**: RAG/MCP 내부 구조와 질문 라우팅, 데이터 조회 흐름을 직접 발표·시연하고 기술 질의응답을 맡았습니다. 고객 운영계 도입 전 단계의 PoC였습니다.
- **MES Backend / Data**: MyBatis와 FreeMarker로 일·주·월·부분주 동적 SQL을 구현했습니다. 허용 컬럼 whitelist, parameter binding, 기간 경계와 합계 정합성을 서버에서 처리했습니다.
- **Delivery / Observability**: Jenkins Backend CI/CD와 Ansible backend role/playbook을 구현했습니다. LLM 런타임 설정을 정비하고 Grafana, OpenTelemetry, Loki, Tempo, Mimir 기반 관측 작업에 참여했습니다.

<details>
<summary><b>기여 범위</b></summary>

- **직접 구현**: RAG 평가 하네스·골든셋, 문서 ingestion·청킹·검색 안정성, 7개 MES MCP 조회 영역, 동적 SQL, Backend 배포 role, 일부 알림·관측 개선
- **공동 수행**: Oracle→PostgreSQL 전환, 서버 이관, PostgreSQL·관측성 자동화, Jenkins·Ansible 운영 흐름
- **설계·검토**: pg_dump와 pgBackRest/PITR 도입 방향, GraphRAG 단계적 도입 타당성

</details>

## Database / DBA Engineering

| 영역 | 수행 내용 | 기여 경계 |
| --- | --- | --- |
| DB Migration | Oracle 전용 날짜·문자열·null 처리, JDBC/NLS 의존, MyBatis SQL과 프로시저의 PostgreSQL 전환 및 화면 동작 검증 | 전체 전환은 팀 작업 |
| Schema Change | Liquibase 멀티테넌트 구조, schema hardcoding·checksum 문제, 설정·감사 스키마 changeset과 changelog 순서 관리 | 담당 범위 직접 수행 |
| MES SQL | 수요·생산·자재소요·발주 데이터를 일·주·월·부분주로 조회하는 MyBatis + FreeMarker 동적 SQL 구현 | 직접 구현 |
| Data Integrity | 허용 컬럼 whitelist, parameter binding, 기간 경계, subtotal·total, null·반올림과 upsert 조건을 서버에서 처리 | 직접 구현 |
| Backup / Recovery | pg_dump 기반 단기 전략, WAL/PITR·pgBackRest 단계적 도입, 단일 DB·전체 복구 절차와 검증 쿼리 문서화 | 설계·검토 |
| DB Observability | PostgreSQL exporter와 Grafana 환경에서 pg_up false alert, NoData·중복 알림 조건 보완 | 공동 환경의 일부 개선 |

DB 객체 개수나 전체 마이그레이션 규모는 팀 범위이므로 개인 성과 수치로 사용하지 않습니다. 구축하지 않은 pgBackRest·PITR도 완료 경험처럼 쓰지 않습니다.

## Selected Projects

### [MES Document MCP](https://github.com/sjMun09/MES-mcp) · 개인 프로젝트

Excel, PDF, Word, Markdown, CSV를 안전하게 다루는 제조 문서용 MCP 서버입니다.

```text
source file
→ secure ingest
→ DocumentIR + source provenance
→ MES entity extraction / validation
→ PatchIR proposal
→ dry-run diff
→ approval
→ apply / validate / export
```

LLM이 원본 파일을 바로 수정하지 못하게 했습니다. 수정은 PatchIR 제안, dry-run, 사용자 승인과 결과 검증을 거쳐야 합니다. AI 코딩 에이전트를 활용했고 요구사항, 안전 정책, 테스트 기준과 공개 전 검증은 직접 설계·검토했습니다.

### [BookKing](https://github.com/BigFunnyMountain/bookKing) · 팀 프로젝트

중앙도서관 OpenAPI 데이터를 수집·적재하고 Elasticsearch로 검색하는 도서 플랫폼입니다. 사용자·검색 영역과 Elasticsearch/Kibana를 담당했습니다. 저장소에 기록된 동일 부하 시나리오에서 JPA 검색 대비 평균 응답시간은 `1,706ms → 85ms`, 처리량은 `27.97 → 559.89 req/s`였습니다.

### [count10](https://github.com/countdown10/count10shop) · 팀 프로젝트

수량 제한과 1인 1회 조건이 있는 쿠폰 도메인과 JMeter 테스트를 담당했습니다. JPA 비관적 락과 Redis 분산 락을 비교하며 중복 발급, 처리량, 응답시간을 같은 시나리오로 검증했습니다.

## DBA Work → AI Application

```text
Oracle / PL/SQL 분석
→ PostgreSQL / Liquibase 변경 관리
→ MES SQL·프로시저·데이터 정합성
→ RAG 지식문서·pgvector 검색
→ MCP read-only 업무 조회
→ 평가·배포·관측 가능한 AI application
```

- **스키마와 프로시저 분석**은 RAG 문서의 필수값·기본값·필터 조건을 검증하는 기준이 됐습니다.
- **테넌트·권한 경계**는 MCP가 회사·사용자·언어 문맥을 명시적으로 전달하고 read-only API만 호출하게 만든 기준이 됐습니다.
- **Liquibase 변경 관리** 경험은 임베딩 모델별 collection과 환경별 LLM DB 변경을 재현 가능하게 관리하는 관점으로 이어졌습니다.
- **DB 관측과 복구 관점**은 retrieval, rerank, generation 지연과 오류를 남기고 실패 시 fallback을 설계하는 습관으로 이어졌습니다.

DBA 경력은 과거 이력이 아니라, AI가 어떤 데이터를 왜 읽었는지 설명하고 장애 뒤에도 복구할 수 있게 만드는 현재의 기반입니다.

## How I Work

1. **원본부터 확인합니다.** 화면 설명만 보지 않고 코드, SQL, 프로시저, 테이블과 가이드를 대조합니다.
2. **같은 조건으로 측정합니다.** 변경 전후를 같은 질문셋, 요청 경로와 지표로 비교합니다.
3. **실패 경로를 먼저 봅니다.** 빈 rerank 결과, provider 오류, 캐시 오염과 latency 증가를 숨기지 않습니다.
4. **기여 범위를 구분합니다.** 직접 구현, 공동 수행, 설계·검토를 섞어 쓰지 않습니다.
5. **결정과 검증을 기록합니다.** 재현 가능한 테스트와 기술 기록을 다음 작업의 출발점으로 남깁니다.

## Tech Stack

| Area | Stack |
| --- | --- |
| LLM Application | Python, FastAPI, RAG, MCP, RAGAS, pgvector, BM25, hybrid retrieval, reranking, embedding, SSE |
| Backend / Data | Java, Spring Boot, MyBatis, FreeMarker, PostgreSQL, Oracle, PL/SQL, PL/pgSQL, Liquibase, MySQL, Redis, Elasticsearch |
| Delivery / Observability | Docker, Jenkins, Ansible, Linux, Grafana, OpenTelemetry, Loki, Tempo, Mimir |
| Test / Validation | pytest, JUnit 5, JMeter, golden set, retrieval evaluation, CI |

## Direction

장기 목표는 문서와 업무 데이터의 수집·정제·검증·저장·서빙부터 AI의 근거와 도구 호출까지 이어지는 **Data + AI pipeline**을 설계하고 구축하는 것입니다. 지금은 실제 MES에서 구현하고 검증한 RAG, MCP, 데이터와 운영 흐름부터 증명하고 있습니다.

## Background & Links

- 동명대학교 컴퓨터공학 학사 · 2024.08
- 가야건설 현장 업무·사내 웹 기능 개발 · 2021.09 - 2024.12
- TechLog: [sj-techlog.pages.dev](https://sj-techlog.pages.dev)
- GitHub: [github.com/sjMun09](https://github.com/sjMun09)
- Email: [ohoh7391@naver.com](mailto:ohoh7391@naver.com)
