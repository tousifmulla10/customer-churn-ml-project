# Task 2: ML Problem Framing & Responsible Data Card

**Goal:** Decide whether machine learning is justified for a real business decision (customer churn), and document the data, harms, and fallback plan before any model training.

## Contents

| File | What it covers |
|---|---|
| [`ml-problem-framing-memo.md`](./ml-problem-framing-memo.md) | The decision, prediction target, unit of observation, action window, non-ML baseline, and a **recommendation against training ML on this dataset** (n=12, plus a suspicious perfect split by `plan_type`). Also covers metrics/costs and abstention/monitoring/rollback design. |
| [`responsible-data-card.md`](./responsible-data-card.md) | Full data card for `customer-churn-training.csv`: purpose, provenance, population, feature/target/leakage notes, quality checks, risks & safeguards, and the intended evaluation plan. |
| [`baseline-notebook.ipynb`](./baseline-notebook.ipynb) | Executed notebook comparing a simple non-ML heuristic rule against a logistic regression baseline (with leave-one-out cross-validation), including the results table and honest caveats about the tiny sample size. |
| [`risk-register.md`](./risk-register.md) | 10 tracked risks (data adequacy, leakage, fairness, privacy, monitoring, rollback) with likelihood, impact, mitigation, and owner. |
| [`Customer-Churn-ML-Framing-Combined.docx`](./Customer-Churn-ML-Framing-Combined.docx) | All four documents combined into a single Word file, for a one-file submission if needed. |

## Key takeaway

The provided dataset (`customer-churn-training.csv`, 12 rows) is useful for prototyping the pipeline and schema, but **is not large or verified enough to train a deployable model**. Every `Basic`-plan customer in the file churned and every `Standard`/`Pro` customer did not — a perfect split that likely reflects how the sample was picked rather than a real-world pattern. The memo and data card recommend confirming data provenance and obtaining a properly sized dataset before any model is trained for production use.
