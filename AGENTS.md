# AGENTS.md — go-ledger

Instructions for any AI coding agent (Claude Code, Codex, Cursor, etc.) working in this repository.

## Context

Portfolio and learning project: a double-entry ledger and payment orchestration service in Go, built in public. The owner is using it to grow as a Go backend engineer, so **the learning matters as much as the code**. Career plan: [go-career-roadmap](https://github.com/pv-oliveira/go-career-roadmap) (private).

## Hard rules

- **Never add `Co-Authored-By` or any AI attribution** to commit messages or PR descriptions.
- **No employer code or business logic.** Everything here is generic and built from scratch. Never introduce code, names, or rules from the owner's employer.
- **Design is human-written.** Files in `docs/` (design docs, specs) are authored by the owner. Do not write the first draft. You may review, critique, ask questions, and later convert an approved design into an implementation issue.
- **Critical invariant tests are human-written.** Tests for balance invariants (postings sum to zero, no unauthorized negative balance) and idempotency are written by the owner. You may implement other code and tests, and you may review these.
- Confirm with the owner before force-pushing, rewriting history, or publishing anything.

## Engineering conventions

- Money is `int64` in minor units (cents) plus a currency code. Never use floating point for money.
- Every write endpoint supports an idempotency key.
- Prefer the standard library; add dependencies only with a clear reason.
- Test-first, small increments. `go test ./...` and `go vet ./...` must pass before a commit.
- Public-facing text (README, docs meant for readers, code comments, commit messages) in English. Conversation with the owner may be in Portuguese.

## Workflow

1. Owner writes or updates a design doc in `docs/`.
2. Agent reviews it and turns it into a scoped issue.
3. Agent implements in small, test-first steps; owner reviews every line before merge.
4. The README's "How this project is built" section documents this workflow — keep it accurate.

## Roadmap

v1 accounts + transfers + idempotency + PostgreSQL · v2 transactional outbox + Kafka + OpenTelemetry/Prometheus + load tests · v3 Docker/Kubernetes + CI/CD + IaC · v4 MCP server for agent-driven queries and reconciliation.
