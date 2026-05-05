# model-123

`model-123` is a Codex skill for end-to-end clinical prediction model research workflows.

It is designed for clinical researchers who need structured support for:

- reviewing and optimizing prediction-model research proposals;
- searching literature and converting evidence into study-design suggestions;
- inspecting raw clinical datasets for missingness, coding, formulas, outliers, and leakage risk;
- finalizing reproducible analysis plans;
- running statistical analysis and machine-learning model development;
- generating tables, publication-style figures, model outputs, and risk calculators;
- reviewing the full analysis process and proposing improvements;
- drafting a complete Chinese manuscript for a clinical prediction model study.

## Installation

Copy the whole `model-123` folder to your Codex skills directory:

```text
C:\Users\<your-user-name>\.codex\skills\model-123
```

After installation, start a new Codex session and invoke:

```text
$model-123
```

## Directory Structure

```text
model-123/
  SKILL.md
  README.md
  agents/
    openai.yaml
  references/
    workflow-checklist.md
    outputs.md
    reporting-guidance.md
```

## Workflow Covered

1. Research proposal review
2. Literature search and study-design advice
3. Raw data inspection and quality control
4. Final protocol and statistical analysis plan
5. Reproducible modeling and validation
6. Statistical tables and publication figures
7. Model interpretation and clinical translation
8. Analysis review and improvement suggestions
9. Chinese manuscript drafting

## Methodological Principles

- Preserve raw data and write all outputs to timestamped folders.
- Never fabricate external validation data or publication results.
- Avoid outcome leakage and predictors measured after outcome ascertainment.
- Fit imputation, scaling, feature selection, and tuning only within the training set.
- Report discrimination, calibration, clinical utility, and uncertainty, not AUC alone.
- Prefer interpretable penalized regression as the main model when sample size or event count is limited.
- Use TRIPOD+AI and PROBAST+AI as reporting and bias-assessment frameworks.

## Notes

This repository contains only the reusable Codex skill instructions. It does not contain patient data, analysis outputs, or manuscript files.
