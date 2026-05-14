# Cost Control Checklist

Checklist for reviewing whether an AI system can control, predict, and optimize operational costs.

## 1. Cost Visibility

- [ ] Token usage is tracked per request.
- [ ] Token usage is tracked per user, workflow, or tenant where relevant.
- [ ] Model cost is estimated per workflow.
- [ ] Total daily and monthly AI provider cost is monitored.
- [ ] Cost trends are reviewed regularly.

## 2. Model Selection

- [ ] The system does not use the most expensive model by default.
- [ ] Model choice is matched to task complexity.
- [ ] Cheaper or smaller models are used for simple tasks.
- [ ] Expensive models are reserved for high-value or high-difficulty tasks.
- [ ] Model routing decisions are documented.

## 3. Prompt and Context Efficiency

- [ ] Prompts avoid unnecessary tokens.
- [ ] Retrieved context is filtered before being sent to the model.
- [ ] Repeated static instructions are minimized where possible.
- [ ] Large documents are summarized or chunked before model use.
- [ ] Context size is monitored.

## 4. Caching and Reuse

- [ ] Repeated requests are cached where appropriate.
- [ ] Expensive intermediate results are reused.
- [ ] Embeddings are not recomputed unnecessarily.
- [ ] Retrieval results are cached where useful.
- [ ] Cache invalidation rules are defined.

## 5. Rate Limits and Quotas

- [ ] Usage limits exist per user, tenant, or workflow.
- [ ] Abuse prevention is implemented.
- [ ] Provider rate limits are understood.
- [ ] The system handles rate-limit errors gracefully.
- [ ] Cost spikes trigger alerts.

## 6. Background Processing

- [ ] Expensive AI tasks are moved to background jobs where appropriate.
- [ ] Batch processing is used where possible.
- [ ] Long-running jobs have timeout limits.
- [ ] Failed jobs do not retry indefinitely.
- [ ] Retry policies consider cost impact.

## 7. Business Alignment

- [ ] Cost per request is compared with business value.
- [ ] High-cost workflows have clear justification.
- [ ] Pricing or usage limits account for AI provider costs.
- [ ] Margin risk is understood.
- [ ] Cost assumptions are documented.

## 8. Red Flags

- [ ] No one knows the average cost per request.
- [ ] Token usage is not logged.
- [ ] Every task uses the strongest model.
- [ ] Context is sent without filtering.
- [ ] Failed jobs retry endlessly.
- [ ] Cost spikes are only noticed after the invoice arrives.