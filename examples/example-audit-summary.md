# Example Audit Summary

This is a fictional example showing what a completed AI production readiness audit summary could look like. The system, findings, and recommendations are illustrative.

## System Context

**Product:** Customer-facing AI assistant for answering questions from internal company documents.  
**Current stage:** Beta  
**Users:** Internal support and operations teams (~40 users)  
**Main AI workflow:** User question → retrieval from document index → LLM answer generation → source references returned

---

## Overall Readiness

**Readiness level:** Medium

The system has a working AI workflow and basic access control, but production readiness is limited by weak observability, missing evals, unclear cost tracking, and incomplete retrieval permission checks. It is usable for limited beta testing but not yet suitable for wider rollout.

---

## Scorecard

| Area | Status | Notes |
|---|---|---|
| Architecture | Yellow | Main components exist, but workflow boundaries and failure paths are not fully documented. |
| Reliability & Failure Handling | Yellow | Basic error handling exists, but no configured timeouts or defined fallback behavior. |
| Observability | Red | No request-level tracing. Token usage and costs are not tracked. |
| Evals & Quality | Red | No automated eval dataset or regression testing process. |
| RAG & Context Design | Yellow | Retrieval works, but result ranking and permission checks need review. |
| Cost Control | Red | Cost per request is unknown. No token usage logging. |
| Security & Privacy | Yellow | Basic access control exists. Retrieval does not consistently enforce user-level permissions. |
| Deployment & Release | Yellow | Deployment works, but prompt and config rollback process is not defined. |
| Governance & Risk | Yellow | No documented owner for AI behavior. No process for reviewing prompt changes. |

---

## Key Findings

### Finding 1 — Missing request-level tracing

**Area:** Observability  
**Severity:** High

The system cannot trace a user request across retrieval, LLM call, and final response generation. There is no request ID attached to logs.

**Risk:** Failures are difficult to diagnose. Quality and latency issues may only be discovered through user complaints, by which point they may have persisted for days.

**Recommendation:** Add request IDs to all log entries. Emit structured logs at each step: retrieval query and results, LLM call inputs and outputs, final response, and any errors.

---

### Finding 2 — No evaluation dataset

**Area:** Evals & Quality  
**Severity:** High

The system does not have a representative test set for validating answer quality after prompt, model, or retrieval changes.

**Risk:** Quality regressions can be shipped undetected. There is no way to know whether a prompt change improved or degraded output.

**Recommendation:** Build an initial eval dataset of 30–50 test cases drawn from real user questions, known edge cases, and observed failures. Run evals before any prompt or model change.

---

### Finding 3 — Unknown cost per request

**Area:** Cost Control  
**Severity:** Medium

Token usage and model cost are not tracked per workflow or user.

**Risk:** Cost may scale unpredictably as usage grows. There is no visibility into which workflows or users drive cost.

**Recommendation:** Log input tokens, output tokens, model name, and estimated cost per LLM call. Attach request and user identifiers so cost can be attributed.

---

### Finding 4 — No timeout or fallback on LLM calls

**Area:** Reliability & Failure Handling  
**Severity:** Medium

LLM API calls have no configured timeout. If the provider is slow or unresponsive, requests hang until the client disconnects. There is no fallback message or graceful degradation.

**Risk:** A provider slowdown causes all in-flight requests to stall. Users see no response or a generic application error. During a provider incident, the system offers no useful behavior.

**Recommendation:** Set an explicit timeout on every LLM API call (starting point: 30s for synchronous user-facing requests). Define a fallback response for timeout and provider error cases. Log retry attempts and timeout events separately so provider reliability can be tracked over time.

---

### Finding 5 — No named owner for AI behavior

**Area:** Governance & Risk  
**Severity:** Low

There is no documented owner for the AI system's behavior, prompt configuration, or model selection. Prompt changes have been made ad hoc without a review process.

**Risk:** Behavioral changes can be introduced without review. If the system produces harmful or incorrect output, accountability is unclear. As the user base grows, this becomes a compliance and reputational risk.

**Recommendation:** Designate a named owner for AI behavior. Establish a lightweight review step before prompt or model changes are deployed — even a peer review in a pull request is sufficient at this stage. Document what the system is and is not permitted to do.

---

## Prioritized Roadmap

### Immediate Fixes

- Add request IDs and structured logging across the full AI workflow.
- Log model name, token usage (input and output), latency, and errors for every LLM call.
- Build an initial eval dataset with 30–50 representative test cases.
- Add explicit permission checks to retrieval results before inserting into context.

### Next Improvements

- Add a dashboard for latency, error rate, and token usage.
- Version prompt templates and link deployed version to logs.
- Define rollback process for prompt and model changes.
- Categorize and track user-reported bad answers.
- Name an owner for AI behavior and define a prompt change review process.

### Later Improvements

- Add model routing for simple versus complex requests.
- Add per-user or per-team cost budgets.
- Add automated regression testing to the CI pipeline.
- Add source confidence scoring for retrieved context.

---

## Final Recommendation

The system is acceptable for limited beta use with a small internal group. It should not be expanded to a wider user base or treated as production-ready until observability, evals, retrieval permissions, and cost tracking are in place. Immediate fixes are estimated at 2–3 engineering weeks.
