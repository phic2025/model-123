---
name: model-123
description: End-to-end clinical prediction model research workflow for Codex. Use when the user asks to review or optimize a prediction-model research proposal, search or synthesize literature for study design, inspect raw clinical datasets, finalize a protocol, run reproducible statistical analysis and machine-learning modeling, generate tables and publication-quality figures, review the analysis process, propose improvements, or draft a complete Chinese manuscript for a clinical prediction model study.
---

# Model 123

Use this skill for clinical prediction-model research projects, especially retrospective cohort studies that need a reproducible workflow from protocol review to final manuscript.

## Operating Principles

- Treat the workflow as a clinical study, not just a coding task.
- Preserve raw data. Never overwrite original files; write cleaned data, results, logs, figures, models, and manuscripts to a timestamped output folder.
- Base all statistics and modeling on the real provided dataset. Do not fabricate external validation data or publication results.
- Keep prediction factors temporally prior to outcome determination. Avoid variables that define or leak the outcome in the main model.
- Do all imputation, scaling, feature selection, and hyperparameter tuning inside the training set or cross-validation folds.
- Report model performance beyond AUC: PR-AUC, Brier score, calibration, sensitivity/specificity, F1, DCA, and risk stratification.
- Prefer interpretable, penalized regression as the main model when sample size/events are limited. Use complex machine-learning models as supplements unless they are clearly superior and stable.
- Follow TRIPOD+AI for reporting and PROBAST+AI for bias/applicability thinking.

## Standard Workflow

### 1. Review The Research Proposal

Check whether the draft clearly defines:

- Research question, target population, index time, prediction horizon, intended use, and clinical setting.
- Inclusion/exclusion criteria and whether all predictors are available before outcome determination.
- Outcome definition, adjudication source, and audit trail.
- Candidate predictors, composite-index formulas, units, and timing.
- Planned data split, internal validation, external validation, sensitivity analyses, and reporting standards.

Flag problems as:

- **Must fix**: outcome leakage, unclear outcome definition, non-reproducible data handling, impossible validation, inconsistent formulas.
- **Should improve**: unclear variable timing, excessive model complexity, weak external validation plan, missing calibration/DCA.
- **Acceptable**: minor wording or formatting issues.

### 2. Search And Synthesize Literature

Browse when the user requests literature, current standards, citations, or SCI feasibility. Prefer primary sources:

- Disease definitions and clinical guidelines.
- Prediction-model reporting and bias tools.
- Comparable prediction-model studies.
- Literature defining composite indices and formulas.

Summarize literature as actionable design decisions rather than long background prose. Cite sources in final responses when browsing is used.

### 3. Inspect Raw Data

For spreadsheets or CSV files:

- Read all sheets and confirm dimensions, column names, file timestamp, and encoding.
- Check direct identifiers and whether a de-identified analysis copy is needed.
- Confirm outcome distribution and class balance.
- Check duplicates, unique case IDs, categorical coding, missingness by outcome, and impossible values.
- Recalculate every derived/composite index from source variables.
- Check clinical ranges and logical combinations, for example component totals, score ranges, lipid arithmetic, bilirubin fractions, and unit consistency.

Do not silently edit the raw file. Report issues with row/case IDs and suggested handling.

### 4. Finalize The Analysis Plan

Lock these before modeling:

- Primary outcome and coding.
- Main candidate predictor set.
- Variables used only for comparison, such as traditional scores.
- Missing-data rules.
- Feature-screening and redundancy rules.
- Primary model family and supplemental model families.
- Internal and external validation plan.
- Output list: analysis dataset, code, tables, figures, model object, prediction probabilities, and manuscript.

### 5. Run Reproducible Analysis

Create a timestamped output structure:

```text
analysis_output_YYYYMMDD_HHMMSS/
  data/
  tables/
  figures/
  models/
  manuscript/
  logs/
  code/
```

Minimum outputs:

- De-identified recalculated analysis dataset.
- Train/test split assignment.
- Missingness table.
- Baseline table.
- Composite-index screening table.
- Correlation matrix and high-correlation pairs.
- Cross-validation model-comparison table.
- Test-set model-performance table with confidence intervals.
- Test-set prediction probabilities.
- Final model object and model parameters.

Recommended models:

- Main: Ridge Logistic, LASSO Logistic, Elastic Net Logistic.
- Supplemental: Random Forest, Extra Trees, Gradient Boosting, Hist Gradient Boosting, XGBoost if available, SVM if appropriate.
- Comparators: traditional scores or established clinical scores, not included as main-model predictors if they risk leakage.

### 6. Generate Figures

Use publication-style static figures. Required figures usually include:

- Analysis workflow.
- Outcome distribution or cohort flow.
- Baseline/key variable distributions when useful.
- Composite-index AUC ranking.
- Correlation heatmap.
- ROC and PR curves.
- Calibration curve.
- DCA curve.
- Coefficient/OR forest plot or standardized coefficient plot.
- Variable importance/SHAP or permutation importance.
- Risk stratification observed event rates.

Export both high-resolution PNG and editable SVG/PDF when possible.

### 7. Draft The Manuscript

For Chinese manuscript drafts, use this structure:

- Title.
- Abstract: objective, methods, results, conclusion, keywords.
- Introduction.
- Materials and methods.
- Results.
- Discussion.
- Limitations.
- Conclusion.
- References.

Include exact sample size, event count, split strategy, modeling methods, primary model, test performance, calibration, DCA, and validation limitations. State whether external validation is absent or pending.

### 8. Review And Improve

After analysis, provide a concise methodological review:

- Whether the current evidence supports publication.
- Whether a simpler model is preferable.
- Whether a combined model improves discrimination, calibration, or clinical utility.
- Whether external validation would materially improve the paper.
- What to fix before submission.

Avoid overstating internal-validation results. Highlight when confidence intervals are wide or when traditional comparator scores may contain outcome-defining information.

## References To Load As Needed

- For detailed checklists, read `references/workflow-checklist.md`.
- For expected deliverables and file naming, read `references/outputs.md`.
- For manuscript/reporting guidance, read `references/reporting-guidance.md`.
