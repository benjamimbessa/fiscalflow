# ADR-0001: Event-driven microservices for fiscal document processing

**Status:** accepted · **Date:** 2026-07-20

## Context

In production fiscal systems, document issuance depends on external government web services (SEFAZ) that are slow, rate-limited, and periodically unavailable. In the monolithic architecture I have operated for 16 years, this coupling is managed with contingency modes and queued retries inside a single deployment. The goal of this project is to explore how the same guarantees — a sale is never lost, every document is eventually issued, sequence and auditability are preserved — map to a cloud-native, event-driven design.

## Decision

Split the domain into independently deployable services (Orders, Invoicing, Projections) communicating through durable messaging (SNS/SQS), with a transactional outbox at every producer.

## Consequences

**Gains:** issuance failures no longer block order acceptance; each service scales and deploys independently; the audit trail is the event stream itself.

**Costs:** eventual consistency between order state and document state must be explicit in the API contract; idempotency is mandatory everywhere; local development requires infrastructure emulation (LocalStack).

**Rejected alternative:** modular monolith with in-process events. Simpler and often the right call at this scale — rejected here because the project's purpose is precisely to exercise distributed-system trade-offs.
