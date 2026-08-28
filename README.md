# AI Bubble Index

An auditable, quarterly research dashboard for evaluating whether AI investment
commitments exceed demonstrated economic returns. Version 0.1 deliberately
separates **financial overheating** (`B_t`) from **technology momentum** (`T_t`).

## Run locally

This initial prototype is dependency-free:

```bash
python3 -m http.server 4173
```

Then open `http://localhost:4173`.

## Design commitments

- Every observation has a source, retrieval time, method, estimate type, and
  confidence level.
- Missing or low-quality data remain research variables; they are not silently
  promoted into the composite index.
- The bubble score excludes technological progress. The dashboard presents the
  two measures together as a scenario map.
- A release is not published until it includes a confidence-weighted uncertainty
  interval and a data-quality report.

## Data contracts

`data/schema/` contains linked table contracts for the six raw datasets and
`data/metric-catalog.json` records the v0.1 metrics, operationalizations,
transformations, source families, and index eligibility. The catalog is the
machine-readable methodology, not a dataset of asserted values.

## V0.1 scope

The first collection window is 2022 Q1–2026 Q2. Its initial company panel is
Microsoft, Alphabet, Amazon, Meta, Nvidia, Oracle, OpenAI, and Anthropic.
Core financial indicators feed `B_t`; capability, task-horizon, cost, and
adoption indicators feed the separately reported `T_t`.
