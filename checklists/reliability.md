# Reliability & Failure Handling Checklist

Checklist for reviewing how an AI system handles failures, degradation, and unexpected conditions in production.

## 1. Failure Mode Documentation

- [ ] The system documents what can fail: provider outages, timeouts, malformed outputs, downstream dependency failures.
- [ ] Each failure mode has a defined response: retry, fallback, queue, or fail safely.
- [ ] Critical paths are separated from non-critical paths.
- [ ] Partial failures do not cascade into total system failures.
- [ ] Failure behavior is tested, not just assumed.

## 2. Timeout and Retry Behavior

- [ ] Every LLM API call has a configured timeout.
- [ ] Retry logic uses exponential backoff with jitter, not fixed intervals.
- [ ] Maximum retry count is bounded and documented.
- [ ] Retries are logged individually, including attempt number and delay.
- [ ] The system prevents retry storms under load (cascading retries that amplify failures).

## 3. Fallback Strategies

- [ ] User-facing failures surface a clear, safe message rather than a raw error or blank response.
- [ ] The system can degrade partially — for example, skip retrieval or summarization — without complete failure.
- [ ] Fallback behavior is defined per workflow, not just at the application level.
- [ ] Cached or pre-computed results are served where appropriate during provider failures.
- [ ] The team knows which features can safely degrade and which cannot.

## 4. Provider and Dependency Resilience

- [ ] The system can continue operating if the primary LLM provider is unavailable or rate-limited.
- [ ] Fallback providers or cached responses are configured and tested.
- [ ] Provider-specific failure responses — rate limits, content filtering, model unavailability — are handled explicitly.
- [ ] Rate limit exhaustion does not cause user-visible crashes.
- [ ] Third-party dependency failures are isolated from the core user experience.

## 5. Error Budgets and Reliability Targets

- [ ] Acceptable error rate and latency are defined for each AI workflow.
- [ ] The team knows the current production error rate for LLM calls.
- [ ] Reliability targets are differentiated between critical and non-critical workflows.
- [ ] SLOs or reliability expectations are revisited as the system scales.
- [ ] Production incidents are tracked, reviewed, and drive improvements.

## 6. Testing Failure Scenarios

- [ ] Provider failure is testable in a non-production environment.
- [ ] Timeout behavior is tested with real or simulated slow responses.
- [ ] Malformed or unexpected model output handling is tested explicitly.
- [ ] Load behavior under elevated traffic is understood.
- [ ] Failure injection or chaos testing is used where appropriate.

## 7. Red Flags

- [ ] LLM API calls have no timeout configured.
- [ ] Retries are unbounded or use no backoff.
- [ ] A provider outage takes down the entire system.
- [ ] Users see raw stack traces or empty responses on failure.
- [ ] Failure behavior has never been deliberately tested.
- [ ] The team cannot answer: "What happens when the LLM provider returns a 503?"
