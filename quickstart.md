# 10-Minute AI Production Readiness Self-Check

A fast self-check for identifying the biggest production risks in an AI system.

Score each area as:

- **Green** — acceptable for current stage
- **Yellow** — risk exists, needs improvement
- **Red** — serious production risk

## Self-Check

| Area | Question | Score |
|---|---|---|
| Architecture | Can we explain the full AI workflow end-to-end? | Green / Yellow / Red |
| Observability | Can we trace one user request through the whole system? | Green / Yellow / Red |
| Evals | Do we know if output quality gets worse after prompt, model, or retrieval changes? | Green / Yellow / Red |
| RAG / Context | Do we know why specific context was selected and used? | Green / Yellow / Red |
| Cost Control | Do we know the cost per request, workflow, user, or tenant? | Green / Yellow / Red |
| Security & Privacy | Can users only access data they are allowed to see? | Green / Yellow / Red |
| Deployment | Can we roll back application, prompt, model, and configuration changes? | Green / Yellow / Red |

## Interpretation

### Mostly Green

The system has a healthy production foundation.

Continue with the full checklist to find deeper risks.

### Several Yellow

The system may work, but production risk exists.

Prioritize the yellow areas before usage grows.

### Any Red

Treat this as a serious risk.

Red areas in **security, observability, evals, or deployment** should be fixed before scaling the system.

## Next Step

After this self-check, use the full checklist areas:

- [Architecture](checklists/architecture.md)
- [Observability](checklists/observability.md)
- [Evals](checklists/evals.md)
- [RAG & Context Design](checklists/rag-context.md)
- [Cost Control](checklists/cost-control.md)
- [Security & Privacy](checklists/security-privacy.md)
- [Deployment](checklists/deployment.md)