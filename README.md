# AI Production Readiness Checklist

A structured checklist framework for evaluating whether AI and LLM systems are ready for production.

This is not a certification or guarantee of readiness. It is a practical review tool — a set of concrete questions designed to surface risks, gaps, and missing controls before they become expensive production problems.

---

## Table of Contents

- [What this is](#what-this-is)
- [Who this is for](#who-this-is-for)
- [How to use it](#how-to-use-it)
- [Checklist areas](#checklist-areas)
- [Templates](#templates)
- [Example](#example)
- [Limitations](#limitations)
- [License](#license)

---

## What this is

Building an AI prototype is relatively straightforward. Running a reliable AI system in production is harder.

Common failure points include:

- no tracing or observability across LLM calls
- no way to detect quality regressions after prompt or model changes
- uncontrolled cost growth as usage scales
- fragile retrieval and context design
- poor failure handling — no timeouts, retries, or fallbacks
- no rollback plan for prompt or model changes
- security and privacy risks from uncontrolled data flows
- no named owner when something goes wrong

This checklist helps identify those risks before they become production incidents.

---

## Who this is for

This framework is useful for:

- **AI engineers and backend engineers** building LLM-based systems
- **Engineering leads and CTOs** evaluating production readiness of an AI system
- **Consultants and architects** conducting AI system reviews
- **Product teams** moving from prototype to production

It assumes a working system exists and asks: *is this actually ready for production use?*

---

## How to use it

There are three ways to use this framework:

**1. Quick self-check (10 minutes)**

Use the [10-Minute Self-Check](quickstart.md) to identify the biggest production risks fast. Good for a first pass before a launch or review.

**2. Full checklist review**

Work through each checklist area below. For each item, assess whether it is in place, partially in place, or missing. Record findings with severity. Use the [Production Readiness Scorecard](production-readiness-scorecard.md) to summarize results.

**3. Structured audit**

Use the [Discovery Questions](templates/discovery-questions.md) to understand the system first. Work through the checklists. Record detailed findings in the [Audit Report Template](templates/audit-report-template.md).

---

## Checklist areas

| Area | What it covers |
|---|---|
| [Architecture](checklists/architecture.md) | System design, workflow boundaries, orchestration, state, dependencies |
| [Reliability & Failure Handling](checklists/reliability.md) | Timeouts, retries, fallbacks, degradation, provider resilience |
| [Observability](checklists/observability.md) | Request tracing, LLM call logging, metrics, alerts, dashboards |
| [Evals & Quality](checklists/evals.md) | Output quality measurement, test datasets, regression testing |
| [RAG & Context Design](checklists/rag-context.md) | Retrieval design, chunking, context construction, grounding |
| [Cost Control](checklists/cost-control.md) | Token usage visibility, model selection, caching, rate limits |
| [Security & Privacy](checklists/security-privacy.md) | Access control, secrets, prompt injection, data handling |
| [Deployment & Release](checklists/deployment.md) | Release process, prompt/model versioning, rollbacks, operational readiness |
| [Governance & Risk](checklists/governance.md) | Accountability, human-in-the-loop, risk assessment, compliance posture |

---

## Templates

| Template | Purpose |
|---|---|
| [Production Readiness Scorecard](production-readiness-scorecard.md) | One-page summary of scores across all areas |
| [Audit Report Template](templates/audit-report-template.md) | Structured template for documenting a full review |
| [Discovery Questions](templates/discovery-questions.md) | Questions for understanding a system before reviewing it |

---

## Example

[Example Audit Summary](examples/example-audit-summary.md) — a fictional example showing what a completed audit summary looks like, including findings, scorecard, and prioritized roadmap.

---

## Limitations

This checklist is a review aid. It will not:

- guarantee production readiness
- replace security review, legal assessment, or domain expertise
- cover every possible AI system architecture or deployment model
- address regulatory requirements specific to your jurisdiction or industry

Passing all checklist items does not mean a system is ready for production. Failing items does not mean it cannot ship. Judgment and context are always required.

**Coverage gaps to be aware of:**

- Latency and performance are addressed across [Architecture](checklists/architecture.md), [Observability](checklists/observability.md), and [Cost Control](checklists/cost-control.md) rather than as a dedicated checklist area.
- The framework is primarily suited to cloud-hosted LLM systems. Self-hosted, on-premise, or edge-deployed models have additional considerations not fully covered here.
- Sector-specific compliance requirements (healthcare, finance, legal) are flagged in [Governance & Risk](checklists/governance.md) but not addressed in detail.
- Multi-agent systems with complex orchestration patterns are partially covered but represent an evolving area.

This is a living framework. It is intentionally practical and opinionated, not a complete academic reference.

---

## License

MIT
