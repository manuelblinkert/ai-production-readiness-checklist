# Evals Checklist

Checklist for reviewing whether an AI system has a reliable way to measure output quality.

## 1. Evaluation Strategy

- [ ] The system defines what a “good” output means.
- [ ] Evaluation criteria are documented.
- [ ] Critical failure modes are defined.
- [ ] The team knows which outputs require high precision.
- [ ] The system distinguishes between acceptable variation and actual failure.

## 2. Test Data

- [ ] There is a representative evaluation dataset.
- [ ] The dataset includes common user inputs.
- [ ] The dataset includes edge cases.
- [ ] The dataset includes adversarial or difficult examples where relevant.
- [ ] Test cases are versioned.

## 3. Automated Evals

- [ ] Automated evals run on important AI workflows.
- [ ] Evals check output format validity.
- [ ] Evals check factual correctness where possible.
- [ ] Evals check instruction following.
- [ ] Evals check safety or policy constraints where relevant.
- [ ] Evals run before major prompt/model changes.

## 4. Human Review

- [ ] Human review exists for high-risk outputs.
- [ ] Reviewers use consistent scoring criteria.
- [ ] Bad outputs are labeled and categorized.
- [ ] Review feedback is used to improve prompts, retrieval, or workflows.
- [ ] Human review results are tracked over time.

## 5. Regression Testing

- [ ] Prompt changes are tested against previous examples.
- [ ] Model changes are tested before deployment.
- [ ] Retrieval/context changes are tested before deployment.
- [ ] Known failure cases are kept in the test suite.
- [ ] Quality regressions block deployment where needed.

## 6. Production Feedback

- [ ] User feedback can be captured.
- [ ] Bad outputs can be reported.
- [ ] Production failures feed back into the eval dataset.
- [ ] Quality trends are monitored over time.
- [ ] Repeated failure patterns are analyzed.

## 7. Red Flags

- [ ] The team relies only on “it feels good” manual testing.
- [ ] No eval dataset exists.
- [ ] Prompt changes are shipped without regression testing.
- [ ] Model upgrades happen without quality comparison.
- [ ] Production failures are not converted into test cases.
- [ ] There is no clear definition of output quality.