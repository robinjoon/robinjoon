# 낭만 개발자 임수빈 입니다

백엔드 API 개발부터 실시간 데이터 파이프라인(Flink CDC), Kubernetes 플랫폼 운영까지 end-to-end로 직접 설계하고 운영한 경험이 있는 백엔드 개발자입니다. 공용 라이브러리 설계, 오픈소스 커스텀, 성능 최적화 등 팀의 기술적 난제를 주도적으로 해결해 왔으며, 배운 것을 사내 기술 공유·블로그·외부 발표로 적극적으로 환원합니다.

📎 [포트폴리오](https://www.notion.so/328e2d0a976a8037b81ec37660f05a2a) · ✍️ [블로그](https://blog.robinjoon.xyz) · ✉️ 0108dlatnqls@gmail.com

# 기술 스택

| 분류 | 기술 |
| --- | --- |
| Language & Framework | **`Kotlin`**, **`Spring Boot`**, **`Exposed ORM`**, **`Netflix DGS`**, `Kotest` |
| Data & Streaming | **`Apache Flink`**, **`Flink CDC`**, **`Kafka`**, `Avro`, `Schema Registry` |
| Infra & Ops | `PostgreSQL`, `MongoDB`, **`Kubernetes`**, `Istio`, `ArgoCD`, `Grafana`, `Prometheus` |

# 경력

## 여기어때컴퍼니 | 숙박플랫폼개선TF (2026.06 ~ 현재)

## (주)커넥트웨이브 플랫폼개발본부 | 플랫폼개발팀 (2024.12 ~ 2026.05)

### 100명 규모 개발 조직 공용 라이브러리 개발 (2건) — 설계 및 구현 주도

> 2개 프로젝트 · 15개 모듈에서 공통으로 사용되는 라이브러리 2건 설계 및 구현

- **Audit Log 라이브러리** — Spring Boot 2.x / 3.x 동시 지원, 저장소 추상화 + AOP 구조로 신규 플랫폼 전체 적용
- **Kotlin Exposed ORM 페이징 라이브러리** — Spring Data `Pageable` 통합, 전체 개발 조직의 페이징 처리 방식 통일

### 상품 저장 시스템 부하 테스트 및 성능 최적화 — 병목 분석 및 개선 주도

> 5만 건 대량 적재 기준 **200초 → 2초 (100배 개선)**

- Thread Dump 기반 병목 분석(MongoDB 예외 누적) → **200초 → 10초**, 이후 Bulk 처리·Scale-out 등 추가 최적화로 최종 **2초** 달성

### AI 버티컬 서비스 관리자 API 및 OpenAI 연동 배치 시스템 구축 — API 및 배치 시스템 구현 담당

> OpenAI Batch API 기반 상품 추천 문구 자동 생성 파이프라인, **토큰 비용 50% 절감**

- 관리자 설정 + 주간 배치 구조로 AI 추천 문구 생성 파이프라인 구축, 블라인드 테스트로 품질 검증
- OpenAI Batch API + 1분 주기 폴링(`tailrec`)으로 안정적 운영 체계 구성

### Apache Flink 기반 CDC 파이프라인 시스템 구축 — 설계 및 구축 주도

> MongoDB → Kafka → Hadoop 실시간 CDC 파이프라인, **평균 3만 TPS / 지연 500ms 미만**

- Flink SQL(Streampark) 프로토타이핑 후 Before/After Diff 처리 한계를 식별, Kotlin DataStream API로 전환
- Kubernetes Flink Operator + ArgoCD GitOps 배포 파이프라인 구축으로 운영 안정성 확보

### Apache Flink CDC Pipeline Kafka Connector 오픈소스 커스텀 개발 — 의사결정 및 구현 담당

> Avro + Schema Registry 미지원 문제를 오픈소스 커스텀으로 해결

- Flink CDC Pipeline YAML의 Avro + Schema Registry 미지원 문제를 확인, 오픈소스 커스텀으로 직접 구현하여 운영 적용
- 유지보수 부담은 AI 에이전트 기반 문서화 자동화로 대응

### 사내 기술 공유

- 사내 K8S 첫 도입 시점에 100명 규모 개발 조직 대상 Kubernetes/Istio 기초 개념~실습 기술 공유 진행

# 프로젝트

## Loop — DDD + Clean Architecture 기반 Kotlin/GraphQL 사이드 프로젝트

🔗 [Spotit-KR/loop](https://github.com/Spotit-KR/loop) · 2026.01 ~ 현재

### AI 에이전트 아키텍처 하네스 설계

- Claude Code Hooks 기반 4종 Python 훅으로 **AI가 계획 없이 코드 수정·PR 생성·위험 명령 실행을 시도할 경우 자동 차단**
- `CLAUDE.md`에 DDD 레이어 규칙·TDD 사이클·이슈 기반 프로세스를 코드화하여 **AI 에이전트가 아키텍처 규칙을 이해하고 따르도록 강제**

### 프로젝트 기술 스택

- Spring Boot 4 / Kotlin / DGS GraphQL Framework / Exposed ORM / PostgreSQL
- GitHub Issues 기반 작업 추적, MCP(Google Drive) 연동

## 데벨업 — 개발자 취준생 커뮤니티 플랫폼 (우아한테크코스 6기 백엔드)

🔗 [woowacourse-teams/2024-devel-up](https://github.com/woowacourse-teams/2024-devel-up) · 2024.06 ~ 2024.11

### 풀이 목록 조회 성능 3배 개선 및 시스템 자원 효율화

- 서비스 진입점이기에 부하 테스트 대상으로 선정. 10만 건 데이터 처리에 700ms 소요
- 쿼리 분할을 통해 응답시간 300ms로 단축, 제출 일자에 인덱스 추가하여 **200ms**로 개선
- 읽기/쓰기 분리 라우팅 알고리즘 수정으로 **TPS 60 → 120 (2배 개선)**

### AWS 분산 인프라 및 무중단 배포 파이프라인 구축

- 단일 EC2에서 시작해 모니터링 시스템(Docker Compose), 로드밸런서 + WAS/DB 다중화까지 점진적으로 인프라 개선
- GitHub Actions 기반 CI/CD 파이프라인 구축, Rolling 방식 무중단 배포 설계 및 운영

# 교육 및 학력

## 우아한테크코스 6기 웹 백엔드 수료 (2024.02 ~ 2024.11)

- 페어 프로그래밍과 코드 리뷰 기반 미션 수행을 통한 TDD, OOP, Clean Code 학습
- 팀 프로젝트를 통한 협업 경험 (기획, 설계, 인프라, 개발)

## 홍익대학교 컴퓨터정보통신공학과 졸업 (2016.03 ~ 2024.02)

# 자격증

정보처리기사 | 한국산업인력공단 | 2023.09

# 기타 활동

## 우아한테크코스 8기 백엔드 코드 리뷰어 (2026.02 ~ 현재)

- 우아한테크코스 교육생의 Java 미션(블랙잭, 자동차 경주, 로또 등) PR에 대한 코드 리뷰 수행
- OOP 설계 원칙, 테스트 전략, 네이밍/가독성, 책임 분리 등을 중심으로 멘토링 톤의 리뷰를 제공하여 교육생의 성장을 지원
- 리뷰 품질과 효율 향상을 위해 AI(Claude) 기반의 미션별 리뷰 체크리스트 자동 생성 및 PR 분석 워크플로우를 자체 구축하여 활용 중

## 외부 발표

- **Kotlin User Group Seoul 백엔드 밋업** — 「신입 개발자의 Kotlin, Kotest 입문기」 발표 (Kotest Spec, Spring 연동, Rest Docs DSL 등)
