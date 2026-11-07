# go-ledger

A double-entry ledger and payment orchestration service written in Go — built in public as a learning and portfolio project.

> Status: **design phase**. Code lands incrementally; see the roadmap below.

## Goals

- Correct money movement: double-entry bookkeeping, balanced transactions, no floating point.
- **Idempotent** APIs (idempotency keys) safe under retries and concurrent requests.
- Reliable async integration: **transactional outbox** → Kafka.
- Production-grade observability: OpenTelemetry traces, Prometheus metrics, structured logs.
- Runs on Kubernetes with CI/CD and infrastructure as code.
- An **MCP server** so an AI agent can query balances and assist with reconciliation.

## Roadmap

- [ ] v1 — Accounts, transfers, double-entry postings, idempotency keys, PostgreSQL, tests
- [ ] v2 — Transactional outbox + Kafka events, OpenTelemetry/Prometheus, load tests
- [ ] v3 — Docker/Kubernetes deploy, CI/CD, IaC
- [ ] v4 — MCP server for agent-driven queries and reconciliation

## How this project is built (AI-assisted workflow)

1. A written spec/design doc comes first (`docs/`), authored by me.
2. Work is planned in small increments, test-first.
3. AI coding agents may implement parts; every line is reviewed before merge.
4. Tests for critical invariants (balances, idempotency) are written by hand.

## Disclaimer

Independent project built from scratch with generic, public concepts. It contains no code or business logic from any employer.

## License

MIT
