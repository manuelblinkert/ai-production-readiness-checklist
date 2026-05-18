# Architecture Checklist

Checklist for reviewing the system design of an AI system before or during production use. Covers boundaries, workflow design, orchestration patterns, state, dependencies, and maintainability.

## 1. System Boundaries

- [ ] The system has clear boundaries between frontend, backend, AI workflow, data layer, and external services.
- [ ] The LLM is treated as one component of the system, not as the entire system.
- [ ] Business logic is not hidden inside prompts.
- [ ] Prompt logic, retrieval logic, tool calls, and post-processing are separated.
- [ ] Critical workflows are documented end-to-end: inputs, steps, external calls, and expected outputs.

## 2. AI Workflow Design

- [ ] The AI workflow has a clear input and output contract.
- [ ] The system defines what happens before the model call.
- [ ] The system defines what happens after the model call.
- [ ] Model outputs are validated before being used downstream.
- [ ] The workflow handles incomplete, invalid, or low-confidence outputs.

## 3. State and Memory

- [ ] The system clearly defines what state is stored.
- [ ] User-specific memory is separated from global system knowledge.
- [ ] Stored memory has ownership, lifecycle, and deletion rules.
- [ ] The system avoids uncontrolled context accumulation.
- [ ] Important state changes are traceable.

## 4. Dependencies

- [ ] External dependencies are documented.
- [ ] LLM provider failure is handled gracefully.
- [ ] Timeout behavior is defined.
- [ ] Retry behavior is defined.
- [ ] Fallback behavior is defined where needed.

## 5. Scalability

- [ ] Synchronous and asynchronous workloads are separated where appropriate.
- [ ] Long-running AI tasks do not block user-facing requests.
- [ ] Background jobs are used for slow processing.
- [ ] The architecture can handle increased request volume.
- [ ] Bottlenecks are known and documented.

## 6. Maintainability

- [ ] Prompts/configuration are versioned.
- [ ] AI workflow code is testable.
- [ ] The system can be modified without rewriting large parts of the application.
- [ ] Architecture decisions are documented.
- [ ] There is a clear owner for each major subsystem.

## 7. Orchestration and Tool Use

For systems using multi-step chains, tool calls, or agent loops.

- [ ] The orchestration flow has defined start and end conditions — it cannot loop indefinitely.
- [ ] Tool and function call inputs are validated before execution.
- [ ] Tool call outputs are validated before being passed to the next step.
- [ ] The system limits the number of agent steps or tool calls per request.
- [ ] Side effects from tool calls — writes, API calls, external actions — are controlled and auditable.
- [ ] Structured output formats (JSON, schema-constrained) are validated, not assumed to be correct.
- [ ] The system handles tool call failures without crashing the full workflow.

## 8. Red Flags

- [ ] One giant prompt controls core business logic.
- [ ] No clear separation between application logic and AI behavior.
- [ ] No validation of model outputs.
- [ ] No timeout, retry, or fallback strategy.
- [ ] No documentation of data flow.
- [ ] No clear answer to: “What breaks first at 10x usage?”