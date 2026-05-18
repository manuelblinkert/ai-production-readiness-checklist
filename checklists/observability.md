# Observability Checklist

Checklist for reviewing whether an AI system can be monitored, debugged, and operated in production.

## 1. Request Tracing

- [ ] Each user request has a unique request ID.
- [ ] A request can be traced across frontend, backend, AI workflow, database, and external services.
- [ ] Logs include request ID, user/session ID where appropriate, and timestamp.
- [ ] Errors can be connected back to the original request.
- [ ] Long-running background jobs are traceable.

## 2. LLM Call Logging

- [ ] Model provider, model name, and model version are logged.
- [ ] Prompt template name or version identifier (hash, name, or git ref) is logged alongside each LLM call so behavior changes can be traced to a specific prompt version.
- [ ] Token usage is tracked.
- [ ] Latency per model call is tracked.
- [ ] Error responses from the provider are logged.
- [ ] Retries and fallback attempts are logged.

## 3. Output Monitoring

- [ ] Invalid model outputs are detected.
- [ ] Low-confidence or uncertain outputs are tracked.
- [ ] User-reported bad outputs are stored.
- [ ] Hallucination or factuality issues can be categorized.
- [ ] Safety/security failures are logged separately.

## 4. Metrics

- [ ] Request volume is monitored.
- [ ] Error rate is monitored.
- [ ] Latency is monitored.
- [ ] Token usage is monitored.
- [ ] Cost is monitored.
- [ ] Retry rate is monitored.
- [ ] Timeout rate is monitored.

## 5. Alerts

- [ ] Alerts exist for elevated error rates.
- [ ] Alerts exist for provider failures.
- [ ] Alerts exist for abnormal cost spikes.
- [ ] Alerts exist for latency degradation.
- [ ] Alerts exist for failed background jobs.
- [ ] Alert severity levels are defined.

## 6. Debuggability

- [ ] Engineers can inspect failed AI workflows.
- [ ] Prompt inputs and model outputs are available where safe and compliant.
- [ ] Sensitive data is redacted or protected.
- [ ] System behavior can be reproduced from logs where possible.
- [ ] There is a clear incident investigation process.

## 7. Dashboards

- [ ] There is a dashboard for system health.
- [ ] There is a dashboard for LLM usage and cost.
- [ ] There is a dashboard for latency and errors.
- [ ] There is a dashboard for eval or quality metrics if applicable.
- [ ] Dashboard ownership is clear.

## 8. Red Flags

- [ ] AI failures are only discovered through user complaints.
- [ ] No request IDs.
- [ ] No token or cost tracking.
- [ ] No prompt/model version tracking.
- [ ] No way to inspect failed workflows.
- [ ] Logs contain sensitive data without protection.