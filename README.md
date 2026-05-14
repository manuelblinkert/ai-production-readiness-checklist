# AI Production Readiness Checklist

A practical checklist for evaluating whether an AI system is ready for production.

This repository focuses on the engineering realities behind production AI systems: LLM workflows, backend architecture, observability, evals, reliability, cost control, RAG/context design, deployment, and security.

## Quickstart

Start with the [10-Minute AI Production Readiness Self-Check](quickstart.md).

Use it to quickly identify the biggest production risks before going into the full checklist.

## Who this is for

This checklist is useful for:

- AI startup founders
- CTOs and engineering leads
- backend engineers building LLM systems
- product teams moving from prototype to production
- consultants reviewing AI system architecture

## Why this exists

Building an AI prototype is easy.

Running a reliable AI system in production is harder.

Common failure points include:

- unclear architecture boundaries
- weak observability
- missing evals
- uncontrolled cost growth
- fragile RAG/context design
- poor failure handling
- latency problems
- security and privacy risks
- no deployment or rollback strategy

This checklist helps identify those risks before they become expensive production problems.

## Checklist Areas

- [Architecture](checklists/architecture.md)
- [Observability](checklists/observability.md)
- [Evals](checklists/evals.md)
- [RAG & Context Design](checklists/rag-context.md)
- [Cost Control](checklists/cost-control.md)
- [Security & Privacy](checklists/security-privacy.md)
- [Deployment](checklists/deployment.md)

## Templates

- [Audit Report Template](templates/audit-report-template.md)
- [Discovery Questions](templates/discovery-questions.md)

## Example

- [Example Audit Summary](examples/example-audit-summary.md)

## How to use this

Use this repository as a practical review framework.

For each checklist area:

1. Review the current system.
2. Identify risks and missing controls.
3. Assign severity.
4. Prioritize fixes.
5. Convert findings into an implementation roadmap.

For a faster first pass, use the [10-Minute Self-Check](quickstart.md).

## Status

This is a living checklist. It is intentionally practical and opinionated, not a complete academic framework.

## License

MIT