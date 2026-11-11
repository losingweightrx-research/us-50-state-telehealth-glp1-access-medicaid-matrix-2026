---
license: cc-by-4.0
language:
  - en
pretty_name: "US 50-State + DC Telehealth Modality, Medicaid GLP-1 Coverage & Local Clinic Cost Matrix (2026)"
size_categories:
  - n<1K
task_categories:
  - tabular-regression
  - tabular-classification
tags:
  - healthcare
  - pharmacoeconomics
  - telehealth
  - glp-1
  - health-policy
configs:
  - config_name: default
    data_files:
      - split: train
        path: state_access_matrix.csv
  - config_name: medicaid_obesity_covered_states
    data_files:
      - split: train
        path: subsets/medicaid_obesity_covered_states.csv
  - config_name: async_telehealth_permitted_states
    data_files:
      - split: train
        path: subsets/async_telehealth_permitted_states.csv
  - config_name: strict_sterile_compounding_board_states
    data_files:
      - split: train
        path: subsets/strict_sterile_compounding_board_states.csv
---

# US 50-State + DC Telehealth Modality, Medicaid GLP-1 Coverage & Local Clinic Cost Matrix (2026)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24139340.svg)](https://doi.org/10.5281/zenodo.24139340)

**Published by:** Losing Weight RX Pharmacoeconomics & Consumer Audit Desk (Losing Weight RX LLC)  
**Canonical Interactive Dataset Hub:** [https://losingweightrx.com/datasets/us-50-state-telehealth-glp1-access-medicaid-matrix-2026/](https://losingweightrx.com/datasets/us-50-state-telehealth-glp1-access-medicaid-matrix-2026/)  
**Paired Statistical Audit Report:** [https://losingweightrx.com/blog/2026-us-50-state-telehealth-medicaid-glp1-access-report](https://losingweightrx.com/blog/2026-us-50-state-telehealth-medicaid-glp1-access-report)  
**Methodology & Editorial Governance:** [https://losingweightrx.com/editorial-standards](https://losingweightrx.com/editorial-standards)  
**Academic Identifier (DOI):** `10.5281/zenodo.24139340`  
**License:** Creative Commons Attribution 4.0 International (`CC-BY-4.0`)  
**Last Verified:** `2026-11-11`

---

## Executive Summary

51-jurisdiction US regulatory and geographic price-disparity matrix (50 states plus Washington, DC) indexing state telehealth modality rules (asynchronous vs synchronous video), Medicaid adult obesity GLP-1 coverage, state-employee plan formulary status, non-resident 503A board tiers, and local brick-and-mortar medspa vs online flat-rate savings.

All numeric fields are strictly typed (`Float64` / `Int64` / `Boolean`) with zero currency-string symbols or untyped null placeholders, enabling zero-friction ingestion into Apache Parquet, DuckDB, Polars, Pandas, and `datasets.load_dataset("losing-weight-rx/us-50-state-telehealth-glp1-access-medicaid-matrix-2026")`.

## Multi-Configuration Splits Included

| Config Name | File Path | Description |
| :--- | :--- | :--- |
| `default` | `state_access_matrix.csv` | Complete audited dataset (`all` records) |
| `medicaid_obesity_covered_states` | `subsets/medicaid_obesity_covered_states.csv` | Filtered analytical split (`16` records) |
| `async_telehealth_permitted_states` | `subsets/async_telehealth_permitted_states.csv` | Filtered analytical split (`46` records) |
| `strict_sterile_compounding_board_states` | `subsets/strict_sterile_compounding_board_states.csv` | Filtered analytical split (`19` records) |

## Column Schema (`20` Strictly Typed Fields)

- `jurisdiction_record_id`
- `state_name`
- `state_postal_code`
- `census_region`
- `telehealth_initial_exam_modality`
- `async_intake_permitted_boolean`
- `medicaid_adult_obesity_glp1_covered_boolean`
- `state_employee_plan_glp1_active_boolean`
- `nonresident_503a_sterile_board_tier`
- `adult_obesity_prevalence_pct`
- `local_bariatric_medspa_sema_median_usd`
- `local_bariatric_medspa_tirz_median_usd`
- `verified_online_flat_sema_usd`
- `verified_online_flat_tirz_usd`
- `annual_household_sema_savings_usd`
- `annual_household_tirz_savings_usd`
- `prior_auth_commercial_denial_rate_est_pct`
- `cold_chain_express_transit_days`
- `state_access_equity_score_100`
- `official_policy_reference_url`

## Scoring Framework: LWR Consumer Price-Lock & Dose-Parity Index (v1.0)

Records are evaluated deterministically across four verifiable consumer-protection axes:
1. **Dose-Escalation Parity:** Whether high maintenance doses (`2.4 mg` semaglutide / `15.0 mg` tirzepatide) maintain the same monthly rate as starter titration vials (`0.25 mg` / `2.5 mg`).
2. **Fee Unbundling Disclosure:** Whether recurring platform membership fees (`$75-$199/mo`), lab markups, or initial consult charges are separated from medication pricing.
3. **Contractual Exit Freedom:** Month-to-month cancel-anytime billing vs. mandatory 3-, 6-, or 12-month non-refundable upfront locks.
4. **Pharmacoeconomic Yield:** Effective out-of-pocket USD per milligram of active ingredient or bioavailable dose delivered.

## Citation (BibTeX)

```bibtex
@dataset{lwr_us_50_state_telehealth_glp1_access_medicaid_matrix_2026,
  author       = {Losing Weight RX Pharmacoeconomics & Consumer Audit Desk},
  title        = {US 50-State + DC Telehealth Modality, Medicaid GLP-1 Coverage & Local Clinic Cost Matrix (2026)},
  year         = {2026},
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.24139340},
  url          = {https://losingweightrx.com/datasets/us-50-state-telehealth-glp1-access-medicaid-matrix-2026/}
}
```
