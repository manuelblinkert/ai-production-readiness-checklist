# Deployment Checklist

Checklist for reviewing whether an AI system can be deployed, released, rolled back, and operated safely.

## 1. Environments

- [ ] Development, staging, and production environments are separated.
- [ ] Production secrets are not used in development.
- [ ] Staging is close enough to production to catch realistic issues.
- [ ] Environment-specific configuration is documented.
- [ ] Test data and production data are clearly separated.

## 2. Release Process

- [ ] Deployments are repeatable.
- [ ] Changes go through version control.
- [ ] CI checks run before deployment.
- [ ] Tests run before deployment.
- [ ] Deployment steps are documented.
- [ ] Rollback steps are documented.

## 3. Prompt and Model Versioning

- [ ] Prompt templates are versioned.
- [ ] Model changes are tracked.
- [ ] Retrieval/index changes are tracked.
- [ ] Configuration changes are reviewed before release.
- [ ] AI behavior changes can be linked to a specific deployment or config version.

## 4. Rollbacks

- [ ] Application rollbacks are possible.
- [ ] Prompt/configuration rollbacks are possible.
- [ ] Model version rollbacks are possible where provider support allows it.
- [ ] Database migrations have rollback or recovery plans.
- [ ] Rollback ownership is clear.

## 5. Background Jobs and Queues

- [ ] Background workers are deployed separately where appropriate.
- [ ] Failed jobs are tracked.
- [ ] Retry policies are documented.
- [ ] Dead-letter or failure handling exists for repeated failures.
- [ ] Long-running jobs have timeout limits.

## 6. Operational Readiness

- [ ] Health checks exist.
- [ ] Critical dependencies are monitored.
- [ ] Incident response ownership is defined.
- [ ] Logs and dashboards are available after deployment.
- [ ] On-call or escalation process exists where needed.

## 7. Change Safety

- [ ] High-risk changes are released gradually where possible.
- [ ] Feature flags are used where appropriate.
- [ ] AI behavior changes are tested before full rollout.
- [ ] User-facing failures have fallback behavior.
- [ ] Critical workflows are manually verified after deployment.

## 8. Red Flags

- [ ] Production is changed manually without tracking.
- [ ] Prompt changes are made directly in production without versioning.
- [ ] No staging environment exists.
- [ ] No rollback plan exists.
- [ ] Failed background jobs disappear silently.
- [ ] The team cannot answer: “What changed before this failure started?”