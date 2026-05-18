# Production Readiness Scorecard

A one-page scoring sheet for summarizing an AI production readiness review.

Use this alongside the full [checklist areas](README.md#checklist-areas) and [Audit Report Template](templates/audit-report-template.md).

---

## How to score

- **Green** — adequate for current stage; no immediate action needed
- **Yellow** — risk exists; improvement needed before scaling or wider rollout
- **Red** — serious risk; address before production use

---

## Scorecard

| Area | Score | Key Finding | Priority |
|---|---|---|---|
| Architecture | | | |
| Reliability & Failure Handling | | | |
| Observability | | | |
| Evals & Quality | | | |
| RAG & Context Design | | | |
| Cost Control | | | |
| Security & Privacy | | | |
| Deployment & Release | | | |
| Governance & Risk | | | |

---

## Summary

**Overall readiness:** Low / Medium / High

**Biggest blockers:**

1. 
2. 
3. 

**Recommendation:**

---

## Interpreting the scorecard

**All Green**

The system has a healthy production foundation. Continue with deeper review to find non-obvious risks in each area.

**Several Yellow**

The system may function, but production risk exists. Prioritize yellow areas before scaling or expanding user access.

**Any Red**

Treat this as a serious risk. Red areas in security, observability, or failure handling should be resolved before wider deployment.

---

## Next steps

- Use the [Discovery Questions](templates/discovery-questions.md) for an initial system walkthrough.
- Use the individual [checklist files](README.md#checklist-areas) to review each area in depth.
- Use the [Audit Report Template](templates/audit-report-template.md) to document detailed findings.
- Use the [10-Minute Self-Check](quickstart.md) for a faster first pass.
