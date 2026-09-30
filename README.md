# DDM501 — Individual Assignment 1: ML System Design Document

Võ Minh Sang · 25MS13286

**Report:** [`DDM501_Assignment1_25MS13286_VoMinhSang.pdf`](DDM501_Assignment1_25MS13286_VoMinhSang.pdf)
(source: [`report.html`](report.html))

## Scenario

Credit default risk scoring for consumer credit card origination at a Vietnamese consumer finance company. The
system estimates each applicant's probability of missing the next payment and maps it to APPROVE, REVIEW or DECLINE.

## How the report maps to the assignment sections

| Assignment section (weight) | Report section |
|---|---|
| Problem definition (20%) | 1 — context, problem statement, current situation, why ML, stakeholders |
| Requirements analysis (20%) | 2 — functional, non-functional and data requirements |
| Goals and metrics (20%) | 3 — business, system and model goals with thresholds and baselines |
| High-level architecture design (25%) | 4 — diagram, data flow, component table, pipeline stages |
| Trade-offs analysis (15%) | 5 — five design trade-offs plus known risks |

## Figures

| File | Content |
|---|---|
| [`figures/fig1_system_architecture.svg`](figures/fig1_system_architecture.svg) / [`.png`](figures/fig1_system_architecture.png) | System architecture (sources, offline training pipeline, online serving, registry and monitoring) |

## Where the numbers come from

The report separates **measured** results from **design targets**.

- **Measured** on a prototype (UCI "Default of Credit Card Clients" schema: 30,000 rows, 23 features, 23.3% default
  rate, stratified random 80/20 split): ROC AUC 0.745–0.751, PR AUC about 0.54–0.55, and the selection-rate gap between
  sexes. These come from the ML pipeline in the Lab 1 and Lab 2 repositories (`DDM501_Lab1`, `DDM501_Lab2`) and the
  10-run experiment matrix in the `DDM501_Assignment2` repository.
- **Design targets, not yet measured:** the company-side figures (application volumes, the legacy scorecard's AUC,
  review rates, latency and availability targets) are assumptions for a hypothetical deployment, and the report labels
  them as such. Dropping sex as a model input is planned policy. The prototype still uses it.
