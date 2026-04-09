# Mobile Price Analytics — Data Engineering Pipeline

Built with the Mu Sigma DE Skill (5-Stage Medallion Architecture)

## Architecture
Bronze (raw) → Silver (cleaned + DQ flagged) → Gold (aggregated by Brand/OS/Year)

## Pipeline Stats
- Source rows: 15
- Silver rows: 15
- Gold aggregated groups: 13
- DQ Score: 100%
- PII columns masked: 0

## Repository Structure
```
data/
  bronze_raw.csv        ← Raw source data
  transformed.csv       ← Silver: cleaned + audit columns
  gold_aggregated.csv   ← Gold: aggregated by Brand, OS, Release_Year
  dq_scorecard.json     ← DQ check results
  transform_log.json    ← Transformation audit trail
pipeline/
  airflow_dag.py        ← Airflow DAG (daily 6 AM)
reports/
  *.html                ← MuSigma HTML pipeline report
  *.zip                 ← Full bundle
.github/workflows/
  pipeline.yml          ← CI/CD: lint → validate
```

## Schedule
Daily at 6:00 AM UTC — on-call: Vikas Reddy
