# Security & Privacy Checklist

Checklist for reviewing whether an AI system handles data, access, and model interaction safely.

## 1. Data Classification

- [ ] Sensitive data types are identified.
- [ ] User data, internal company data, and public data are separated.
- [ ] Personally identifiable information is documented where relevant.
- [ ] High-risk data flows are mapped.
- [ ] Data retention rules are defined.

## 2. Access Control

- [ ] Users can only access data they are authorized to see.
- [ ] Retrieval respects user, tenant, and role permissions.
- [ ] Admin-only actions are protected.
- [ ] API endpoints enforce authorization.
- [ ] Access control is tested.

## 3. Secrets Management

- [ ] API keys are not stored in source code.
- [ ] Secrets are stored in a secure secret manager or environment configuration.
- [ ] Development, staging, and production secrets are separated.
- [ ] Key rotation is possible.
- [ ] Logs do not expose secrets.

## 4. Prompt Injection and Data Leakage

- [ ] The system treats user input as untrusted.
- [ ] Retrieved documents are treated as untrusted unless verified.
- [ ] Tool calls have explicit permissions.
- [ ] The model cannot access data purely because the user asks for it.
- [ ] The system has safeguards against leaking hidden prompts, internal data, or other users’ information.

## 5. Model Input and Output Handling

- [ ] Model inputs are reviewed for sensitive data exposure.
- [ ] Model outputs are validated before being used downstream.
- [ ] High-risk outputs require review or confirmation.
- [ ] Unsafe outputs are blocked or handled.
- [ ] Stored model outputs follow retention and privacy rules.

## 6. Vendor and Provider Risk

- [ ] AI provider data usage policies are understood.
- [ ] Provider logging and retention behavior is reviewed.
- [ ] Data processing agreements are considered where relevant.
- [ ] Fallback providers are evaluated for equivalent privacy standards.
- [ ] Provider access is limited to necessary data.

## 7. Compliance and Auditability

- [ ] Important AI decisions are auditable.
- [ ] User consent is collected where required.
- [ ] Users can request deletion or correction where applicable.
- [ ] Security incidents can be investigated.
- [ ] Critical actions are logged.

## 8. Red Flags

- [ ] User permissions are ignored during retrieval.
- [ ] Secrets appear in logs or repositories.
- [ ] The system sends all available user data to the model by default.
- [ ] Prompt injection is not considered.
- [ ] Model outputs trigger actions without validation.
- [ ] No one knows what data the AI provider stores.