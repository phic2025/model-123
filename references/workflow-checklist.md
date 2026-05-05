# Prediction Model Research Checklist

## Proposal Review

- Define target population, clinical setting, prediction time point, prediction horizon, and intended model use.
- Ensure predictors are measured before or at the index time and before outcome ascertainment.
- Define outcome adjudication source and adjudicator process.
- Confirm candidate variables, units, formulas, and timing.
- Separate main predictors from comparator scores.
- Specify validation design before looking at test performance.

## Data Review

- Record source file path, timestamp, sheet names, dimensions, and encoding.
- Confirm de-identification and remove direct identifiers from analysis datasets.
- Confirm unique case IDs and no duplicate rows.
- Check outcome coding and distribution.
- Check categorical coding consistency.
- Check missingness overall and by outcome.
- Check formulas for derived variables.
- Check medical ranges and impossible combinations.
- Produce a case-level issue list rather than modifying raw data.

## Modeling Review

- Fit preprocessing only on training data.
- Avoid selecting variables using test data.
- Use stratified splitting for binary outcomes.
- Use cross-validation for tuning.
- Evaluate discrimination, calibration, and clinical utility.
- Prefer penalized logistic regression when events are limited.
- Use complex ML as supplemental evidence unless clearly justified.

## Manuscript Review

- Report sample size, event count, missingness, split method, and all model settings.
- Include exact predictor handling and formulas.
- Report test-set metrics with confidence intervals.
- Include calibration and DCA.
- State whether external validation is absent, pending, or complete.
- Avoid causal language for predictive variables.
