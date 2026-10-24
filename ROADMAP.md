# Roadmap

## Phase 1 — Foundations (week 1)
- [x] Solution scaffolding (.NET 8, central package management)
- [ ] Orders service: tactical DDD (Order aggregate, domain events, value objects)
- [ ] CQRS with MediatR — commands, queries, pipeline behaviors (validation, logging)
- [ ] PostgreSQL persistence with EF Core migrations
- [x] docker-compose local environment (PostgreSQL, LocalStack, DynamoDB Local)
- [ ] CI pipeline: build + unit tests on every PR

## Phase 2 — Event-driven core (week 2)
- [ ] Transactional outbox in Orders (no dual-write)
- [ ] SNS/SQS messaging via LocalStack; idempotent consumers
- [ ] Invoicing service with simulated tax authority (latency, intermittent failures, rejection codes)
- [ ] Retry policies + circuit breaker (Polly)
- [ ] Projection worker → DynamoDB read models; Query API
- [ ] Integration tests with Testcontainers

## Phase 3 — Cloud & operations (week 3)
- [ ] Terraform: VPC, ECS Fargate, SNS/SQS, RDS PostgreSQL, DynamoDB, Secrets Manager
- [ ] GitHub Actions deploy pipeline (OIDC to AWS, no long-lived keys)
- [ ] OpenTelemetry instrumentation → CloudWatch (traces, metrics, structured logs)
- [ ] Health checks, graceful shutdown, autoscaling policies
- [ ] Load test + documented scalability results

## Phase 4 — AI layer (week 4)
- [ ] RAG service: fiscal legislation ingestion → pgvector → retrieval + generation
- [ ] MCP server exposing platform tools (query documents, issue invoice, check status)
- [ ] Agentic workflow demo: LLM agent resolving a rejected document end-to-end
- [ ] Architecture write-up + demo video
