# Discovery Questions

Questions for understanding an AI system before reviewing production readiness.

## 1. Product Context

- What does the AI system do?
- Who are the users?
- What business problem does it solve?
- Is this system internal, customer-facing, or both?
- What happens if the AI output is wrong?

## 2. Current Stage

- Is the system a prototype, beta, or production system?
- How many users or requests does it currently handle?
- What parts are already live?
- What parts are still experimental?
- What are the biggest known pain points?

## 3. Architecture

- What are the main system components?
- Where does the LLM call happen?
- Is the AI workflow synchronous, asynchronous, or both?
- Are prompts, tools, retrieval, and post-processing separated clearly?
- What external services does the system depend on?

## 4. Data and Context

- What data sources are used?
- Is retrieval used?
- How is context selected, filtered, and ranked?
- How is sensitive data handled?
- Is user-specific memory or state stored?

## 5. Quality and Evals

- How do you know the AI output is good?
- Are there automated evals?
- Are there human review processes?
- Are failures tracked and categorized?
- What are the most common bad outputs?

## 6. Observability

- What logs are collected?
- Can a single request be traced end-to-end?
- Are prompt inputs and model outputs stored safely?
- Are latency, cost, errors, and failure modes monitored?
- Are alerts configured?

## 7. Cost and Performance

- What is the average cost per request?
- What is the acceptable latency?
- Are token usage and model costs tracked?
- Are cheaper/faster models used where possible?
- Is caching used?

## 8. Security and Privacy

- What sensitive data enters the system?
- Are secrets managed properly?
- Are model inputs/outputs access-controlled?
- Are user permissions enforced?
- Are there prompt injection or data leakage risks?

## 9. Deployment and Operations

- How is the system deployed?
- Is there a staging environment?
- Are rollbacks possible?
- Are prompts/configuration versioned?
- Who owns incident response?

## 10. Governance and Risk

- Who is the named owner of this AI system and its behavior in production?
- What is the process for reviewing and approving prompt or model changes?
- Are there workflows where the AI triggers irreversible actions without human review?
- Has legal or compliance reviewed how this system handles user data and AI-generated output?
- Who is responsible when the system produces a harmful or incorrect result?

## 11. Roadmap

- What should this system support in 3–6 months?
- What scaling risks are expected?
- Which technical decisions feel fragile today?
- What would break first if usage increased 10x?