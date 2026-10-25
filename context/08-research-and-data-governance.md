# 08 — Research and Data Governance

## Separate data classes

1. Source research data and ground truth.
2. Evaluation/benchmark datasets derived from source data.
3. Product/demo fixtures.
4. RubroRAG knowledge base documents and vector index.
5. Actual application records from learners/HR.
6. Synthetic or generated test data.

Never mix these classes implicitly. Label provenance, version, permissible use, and storage location.

## Reproducibility

For every research/evaluation run, record dataset version or hash, rubric version, pipeline code commit, retrieval/index version, model/provider and model ID where permitted, prompt/template version, parameters, timestamp, metrics, excluded cases, and known limitations. Preserve raw evaluation output separately from summaries.

Do not use a test result from demo fixtures as evidence for research claims. Do not make results incomparable by changing data preprocessing, evaluator instructions, thresholds, prompts, or model version without documenting the change.

## Existing research notes requiring source verification

Prior working notes mention a study with 520 Vietnamese e-commerce classroom assignments, two raters, and an unweighted-average ground truth; comparisons of Single-Agent and Multi-Agent setups; GPT-5.2 Single-Agent reportedly had better rank correlation on four assignments and beat Multi-Agent on three of four by QWK/rank correlation with lower cost, while the usefulness of multi-agent qualitative feedback was not evaluated. These are unverified working notes in this starter pack, not approved thesis claims. Verify every number, model/version, metric, and conclusion against the actual paper before citing or implementing experimental logic.

## Data safety

- Do not commit raw learner answers, personally identifiable information, credentials, private evaluation sets, or licensed source files without permission.
- Provide sanitized, minimal fixtures for tests.
- Keep access controls and retention policy explicit.
- Redact sensitive information from logs and screenshots.
- If a data file is large or access-restricted, document how an authorized person obtains it without checking it into Git.

## Human review

Keep model output inspectable. Record what was generated and which version/configuration was used. Do not present generated content as ground truth. HR remains accountable for final score and release if that is the approved product policy.
