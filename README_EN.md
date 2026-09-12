# Subin Im — Backend Engineer

A backend engineer with end-to-end experience designing and operating everything from backend APIs to real-time data pipelines (Flink CDC) and Kubernetes platforms. I have taken the lead on my teams' hardest technical problems — shared library design, open-source customization, and performance optimization — and I give back what I learn through internal tech talks and external conference sessions.

📎 [Portfolio](https://www.notion.so/328e2d0a976a8037b81ec37660f05a2a) · ✉️ 0108dlatnqls@gmail.com

# Tech Stack

| Category | Technologies |
| --- | --- |
| Language & Framework | **`Kotlin`**, **`Spring Boot`**, **`Exposed ORM`**, **`Netflix DGS`**, `Kotest` |
| Data & Streaming | **`Apache Flink`**, **`Flink CDC`**, **`Kafka`**, `Avro`, `Schema Registry` |
| Infra & Ops | `PostgreSQL`, `MongoDB`, **`Kubernetes`**, `Istio`, `ArgoCD`, `Grafana`, `Prometheus` |

# Work Experience

## GC Company (Yeogi Eottae) | Accommodation Platform Improvement TF (2026.06 ~ Present)

## Connectwave Inc. | Platform Development Division, Platform Development Team (2024.12 ~ 2026.05)

### Shared Libraries for a 100-Engineer Organization (2 libraries) — Led design and implementation

> Designed and implemented 2 libraries used across 2 projects and 15 modules

- **Audit Log library** — Simultaneous Spring Boot 2.x / 3.x support; storage abstraction plus an AOP-based structure, adopted across the entire new platform
- **Kotlin Exposed ORM pagination library** — Integrated with Spring Data `Pageable`, unifying how the whole engineering organization handles pagination

### Load Testing and Performance Optimization of the Product Storage System — Led bottleneck analysis and improvements

> **200s → 2s (100x improvement)** for a bulk load of 50,000 records

- Thread-dump-based bottleneck analysis (accumulated MongoDB exceptions) brought **200s → 10s**; further optimization via bulk processing and scale-out reached a final **2s**

### Admin API and OpenAI Batch System for an AI Vertical Service — Owned API and batch system implementation

> Automated product recommendation copy generation on the OpenAI Batch API, cutting **token cost by 50%**

- Built the AI recommendation copy pipeline around admin-configured settings and a weekly batch, with blind testing to verify quality
- Established stable operations using the OpenAI Batch API with one-minute polling (`tailrec`)

### Apache Flink CDC Pipeline System — Led design and construction

> MongoDB → Kafka → Hadoop real-time CDC pipeline at **~30K TPS with sub-500ms latency**

- Prototyped with Flink SQL (Streampark), identified its limits in handling before/after diffs, and migrated to the Kotlin DataStream API
- Secured operational stability with a Kubernetes Flink Operator + ArgoCD GitOps deployment pipeline

### Open-Source Customization of the Apache Flink CDC Pipeline Kafka Connector — Owned the decision and implementation

> Solved missing Avro + Schema Registry support through open-source customization

- Identified that Flink CDC Pipeline YAML lacked Avro + Schema Registry support, implemented it directly as an open-source customization, and put it into production
- Offset the maintenance burden with AI-agent-based documentation automation

### Internal Tech Sharing

- Delivered a Kubernetes/Istio session (fundamentals through hands-on practice) to a 100-engineer organization at the time of the company's first K8s adoption

# Projects

## Loop — A Kotlin/GraphQL Side Project Built on DDD + Clean Architecture

🔗 [Spotit-KR/loop](https://github.com/Spotit-KR/loop) · 2026.01 ~ Present

### AI Agent Architecture Harness

- Four Python hooks built on Claude Code Hooks that **automatically block the AI from editing code, opening PRs, or running dangerous commands without a plan**
- Encoded DDD layering rules, the TDD cycle, and an issue-driven process into `CLAUDE.md` so that **AI agents understand and follow the architecture rules**

### Project Stack

- Spring Boot 4 / Kotlin / DGS GraphQL Framework / Exposed ORM / PostgreSQL
- GitHub Issues for task tracking, MCP (Google Drive) integration

## Devel-Up — A Community Platform for Aspiring Developers (Woowa Techcourse 6th, Backend)

🔗 [woowacourse-teams/2024-devel-up](https://github.com/woowacourse-teams/2024-devel-up) · 2024.06 ~ 2024.11

### 3x Faster Solution List Queries and More Efficient Resource Usage

- Selected as a load-testing target as the service's entry point; processing 100,000 records took 700ms
- Split the query to cut response time to 300ms, then added an index on the submission date to reach **200ms**
- Reworked the read/write routing algorithm for **TPS 60 → 120 (2x improvement)**

### Distributed AWS Infrastructure and Zero-Downtime Deployment Pipeline

- Evolved the infrastructure incrementally from a single EC2 instance to a monitoring stack (Docker Compose) and a load balancer with redundant WAS/DB
- Built a GitHub Actions CI/CD pipeline and designed and operated rolling zero-downtime deployments

# Education

## Woowa Techcourse 6th, Web Backend — Completed (2024.02 ~ 2024.11)

- Learned TDD, OOP, and Clean Code through missions based on pair programming and code review
- Gained collaboration experience through team projects (planning, design, infrastructure, development)

## Hongik University, B.S. in Computer and Information Communications Engineering (2016.03 ~ 2024.02)

# Certifications

Engineer Information Processing | Human Resources Development Service of Korea | 2023.09

# Other Activities

## Woowa Techcourse 8th, Backend Code Reviewer (2026.02 ~ Present)

- Review PRs for students' Java missions (Blackjack, Racing Car, Lotto, and more)
- Provide mentoring-toned reviews focused on OOP design principles, testing strategy, naming and readability, and separation of responsibilities to support student growth
- Built and actively use an AI (Claude) based workflow that auto-generates per-mission review checklists and analyzes PRs, improving review quality and throughput

## External Talks

- **Kotlin User Group Seoul Backend Meetup** — "A New Developer's Introduction to Kotlin and Kotest" (Kotest Spec, Spring integration, Rest Docs DSL, and more)
