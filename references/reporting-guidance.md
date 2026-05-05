# Reporting Guidance

## Use Current Standards

- Use TRIPOD+AI for transparent reporting of regression or machine-learning prediction models.
- Use PROBAST+AI to think through risk of bias and applicability.
- Use disease-specific consensus definitions or guidelines for outcomes.

## Results Language

Use cautious predictive wording:

- "associated with higher predicted risk"
- "contributed to the prediction model"
- "improved calibration/probability estimation"
- "showed internal validation performance"

Avoid unsupported causal language:

- "caused severe disease"
- "independent risk factor" unless the model was designed and reported as etiologic inference.

## External Validation

State clearly:

- Development cohort source.
- Internal validation method.
- External validation cohort source, if present.
- Whether external data were collected independently.
- Whether case-mix, outcome definition, and variable measurement are consistent.

If external validation is absent, describe it as a limitation and a future validation priority.

## Common Red Flags

- Test set used for feature selection or model choice.
- Outcome-defining variables used as predictors.
- AUC-only reporting.
- No calibration assessment.
- No confidence intervals.
- Excessive model complexity for limited events.
- Simulated external validation presented as real evidence.
