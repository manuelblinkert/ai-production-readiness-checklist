# Example Audit Summary

This is a fictional example of how an AI production readiness audit summary could look.

## System Context

The system is a customer-facing AI assistant for answering questions from internal company documents.

Current stage: Beta  
Users: Internal support and operations teams  
Main AI workflow: User question → retrieval → LLM answer → source references  

---

## Overall Readiness

**Readiness level:** Medium

The system has a working AI workflow, but production readiness is limited by weak observability, missing evals, unclear cost tracking, and incomplete permission-aware retrieval.

---

## Scorecard

| Area | Status | Notes |
|---|---|---|
| Architecture | Yellow | Main components exist, but workflow boundaries are not fully documented. |
| Observability | Red | No request-level tracing or token/cost tracking. |
| Evals | Red | No automated eval dataset or regression testing. |
| RAG / Context | Yellow | Retrieval works, but ranking and permission checks need review. |
| Cost Control | Red | Cost per request is unknown. |
| Security & Privacy | Yellow | Basic access control exists, but retrieval permissions need stronger validation. |
| Deployment | Yellow | Deployment works, but prompt/config rollback is unclear. |

---

## Key Findings

### Finding 1 — Missing request-level tracing

**Area:** Observability  
**Severity:** High  

The system cannot trace a user request across retrieval, LLM call, and final response generation.

**Risk:** Failures are difficult to debug. Quality and latency issues may only be discovered through user complaints.

**Recommendation:** Add request IDs and structured logs across the full AI workflow.

---

### Finding 2 — No evaluation dataset

**Area:** Evals  
**Severity:** High  

The system does not have a representative test set for validating answer quality after prompt, model, or retrieval changes.

**Risk:** Quality regressions can be shipped without being detected.

**Recommendation:** Build an initial eval dataset from real user questions, edge cases, and known bad outputs.

---

### Finding 3 — Unknown cost per request

**Area:** Cost Control  
**Severity:** Medium  

Token usage and model cost are not tracked per workflow.

**Risk:** Cost may scale unpredictably as usage increases.

**Recommendation:** Log input/output tokens, model name, request type, and estimated cost per request.

---

## Prioritized Roadmap

## Immediate Fixes

- Add request IDs and structured logging.
- Track model, token usage, latency, and provider errors.
- Create an initial eval dataset with 30–50 representative test cases.
- Add permission checks to retrieval results.

## Next Improvements

- Add a dashboard for latency, error rate, and token usage.
- Version prompt templates.
- Define rollback process for prompt and model changes.
- Categorize user-reported bad answers.

## Later Improvements

- Add model routing for simple vs. complex requests.
- Add cost budgets per user or team.
- Add automated regression testing to CI.
- Add source confidence scoring for retrieved context.

---

## Final Recommendation

The system is usable for beta testing, but it should not be treated as fully production-ready until observability, evals, retrieval permissions, and cost tracking are improved.