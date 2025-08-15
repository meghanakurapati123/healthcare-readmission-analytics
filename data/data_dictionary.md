# Data Dictionary — model_input

| Column                 | Type      | Description |
|------------------------|-----------|-------------|
| facility_name          | string    | Hospital name |
| facility_id            | string    | 6-digit hospital ID (zero-padded) |
| state                  | string    | US state code |
| condition              | string    | Friendly label mapped from measure codes |
| measure_id             | string    | READM-30-* HRRP measure code |
| score                  | float     | Main metric (Excess Readmission Ratio or Predicted Rate) |
| predicted_readmission_rate | float | CMS predicted readmission rate (if available) |
| expected_readmission_rate  | float | CMS expected readmission rate (if available) |
| number_of_discharges   | float     | Eligible discharges |
| number_of_readmissions | float     | Observed readmissions |
| readmit_rate_calc      | float     | Computed readmissions/discharges |
| delta_pred_exp         | float     | Predicted - Expected readmission rate |
| ratio_pred_exp         | float     | Predicted / Expected readmission rate |
| risk_band              | category  | Quartile band of `score` (Low→High) |
| high_risk              | 0/1       | 1 if score ≥ 1.05 |
| low_risk               | 0/1       | 1 if score ≤ 0.95 |
| volume_band            | category  | Discharge volume band (Low/Medium/High) |
| score_z_condition      | float     | z-score of `score` within each condition |
| score_z_state          | float     | z-score of `score` within each state |
| start_date             | date      | Period start (if present) |
| end_date               | date      | Period end (if present) |
| period_days            | float     | end_date - start_date in days |
| period_years           | float     | period_days / 365.25 |