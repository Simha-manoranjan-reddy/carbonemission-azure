# ADLS Folder Structure
 
## Overview
 
This project uses Medallion Architecture with separate ADLS Gen2 containers for Bronze, Silver, Gold, Config, and Logs.
 
## Bronze Layer
 
Bronze stores raw source data.
 
bronze/
├── daily_operations/
├── asset_master/
├── emission_factors/
├── carbon_api/
└── reference/
    ├── regions/
    ├── fuel_types/
    └── business_units/

## Silver Layer

Silver stores cleaned and standardized Delta tables

silver/
├── daily_operations_delta/
├── asset_master_delta/
├── emission_factors_delta/
├── region_master_delta/
├── fuel_type_master_delta/
└── business_unit_delta/

## Gold Layer

Gold stores business ready kpi Delta tables

gold/
├── daily_carbon_intensity_delta/
├── asset_emissions_summary_delta/
├── region_emissions_trend_delta/
├── fuel_type_emissions_delta/
├── high_emission_assets_delta/
└── monthly_emissions_summary_delta/

Config Layer

config stores pipeline metadata, control files, schema definitions, and data quality rules

config/
├── pipeline_control/
├── dq_rules/
├── metadata/
└── schema_registry/

Logs Layer

Log stores audit results, pipeline run history, data quality outputs, and error logs

logs/
├── pipeline_audit/
├── dq_results/
├── error_logs/
└── run_history/