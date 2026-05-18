# Governance & Risk Checklist

Checklist for reviewing accountability, risk management, and human oversight in production AI systems.

## 1. Accountability

- [ ] There is a named owner for the AI system and its behavior in production.
- [ ] There is a named owner for prompt and model configuration.
- [ ] Changes to AI behavior require explicit review and approval.
- [ ] The team understands who is accountable when the system causes harm or fails.
- [ ] Incident ownership is clear and documented.

## 2. Human-in-the-Loop

- [ ] High-risk AI outputs require human review before action is taken.
- [ ] The system identifies which output types are high-risk.
- [ ] Human review workflows are defined, staffed, and tested.
- [ ] Humans can override or reject AI decisions.
- [ ] The system is designed to surface uncertainty rather than present low-confidence outputs as definitive.

## 3. Risk Assessment

- [ ] The team has evaluated the impact of wrong AI decisions at scale.
- [ ] Impact scenarios are documented: wrong output, missing output, harmful output.
- [ ] Risk severity is ranked per workflow and use case.
- [ ] Regulatory or legal exposure is understood and documented.
- [ ] External risk reviews are conducted where the system affects high-stakes decisions.

## 4. Prompt and Model Change Governance

- [ ] Prompt changes go through a documented review process.
- [ ] Model upgrades are not deployed without evaluation against the current version.
- [ ] Prompt and model decisions are recorded with rationale.
- [ ] There is a policy defining what the AI system is not permitted to do.
- [ ] Out-of-scope or off-policy behavior is tested and bounded before deployment.

## 5. Bias, Fairness, and Safety

- [ ] The system has been reviewed for outputs that could harm or disadvantage specific user groups.
- [ ] Safety testing covers known failure modes for the specific use case.
- [ ] The team has evaluated how the model handles sensitive topics relevant to the product domain.
- [ ] A process exists for internal and external reporting of harmful outputs.
- [ ] Safety incidents are tracked, reviewed, and used to improve the system.

## 6. Transparency and Documentation

- [ ] The AI system's behavior and limitations are documented for internal stakeholders.
- [ ] Users are informed they are interacting with an AI system where required.
- [ ] Known limitations of the AI system are communicated clearly to users.
- [ ] System changes that affect user experience are communicated.
- [ ] There is a process for handling user concerns or complaints about AI behavior.

## 7. Compliance Posture

- [ ] Applicable regulations are identified (GDPR, EU AI Act, CCPA, HIPAA, sector-specific rules).
- [ ] The team understands how relevant regulations apply to this specific AI system.
- [ ] Data subject rights — access, correction, deletion — can be fulfilled for AI-processed data.
- [ ] Legal review has been conducted where the system affects high-stakes decisions.
- [ ] Compliance requirements are part of the change review process, not an afterthought.

## 8. Red Flags

- [ ] No named owner for the AI system or its production behavior.
- [ ] Prompt and model changes are deployed without review.
- [ ] High-risk AI outputs trigger irreversible actions without human review.
- [ ] Regulatory exposure has not been assessed.
- [ ] The system's behavior and limitations are not documented internally.
- [ ] No process exists to handle a user harmed or disadvantaged by AI output.
