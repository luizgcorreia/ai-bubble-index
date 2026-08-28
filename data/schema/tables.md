# Linked data tables

Each numerical field is an auditable observation and must satisfy
`observation.schema.json` in addition to the table's identifying keys.

| Table | Primary key | Value fields |
| --- | --- | --- |
| `companies` | `company_id` | company, ticker, type, parent, country |
| `financials` | `company_id`, `period` | revenue, gross_profit, operating_income, fcf, capex, debt, cash, market_cap, ev |
| `ai_financials` | `company_id`, `period` | ai_revenue, ai_capex, ai_compute_cost, ai_inference_cost, ai_training_cost, ai_users, paid_users |
| `infrastructure` | `facility_id`, `date` | owner, operator, it_power, h100_equivalent, capital_cost, annual_opex, construction_status |
| `technical` | `model`, `release_date`, `benchmark` | provider, score, inference_price, input_price, output_price, task_horizon_50, task_horizon_80 |
| `macro` | `period` | gdp, gdp_growth, corporate_bond_spread, interest_rate, inflation, productivity, tfp, ai_investment_gdp |

`ai_financials` must retain `estimate_type` whenever `reported_or_estimated` is
`estimated`; annualized run-rate values must not be mixed with reported revenue.
