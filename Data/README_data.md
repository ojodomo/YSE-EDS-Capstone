# Data README — Wind Energy Suitability Analysis for Nigeria

## Dataset: Global Wind Atlas (GWA)

| Field | Detail |
|-------|--------|
| **Source** | Global Wind Atlas v3 (globalwindatlas.info) |
| **Provider** | Technical University of Denmark (DTU) & World Bank Group |
| **File** | `20260130_GWA.csv` |
| **Access Date** | January 30, 2026 |
| **License** | Creative Commons Attribution 4.0 (CC BY 4.0) |
| **Coverage** | 37 administrative units (36 states + FCT), Nigeria |

## Variable Descriptions

| Column | Unit | Description |
|--------|------|-------------|
| `S/N` | — | Serial number (row index) |
| `States` | — | Nigerian state name |
| `Capital` | — | State capital city |
| `Region` | — | One of Nigeria's 6 geopolitical regions |
| `Wind_Speed_10m` | m/s | Mean annual wind speed at 10m hub height |
| `Mean_Power_Density_10m` | W/m² | Mean wind power density at 10m |
| `Wind_Speed_50m` | m/s | Mean annual wind speed at 50m hub height |
| `Mean_Power_Density_50m` | W/m² | Mean wind power density at 50m |
| `Wind_Speed_100m` | m/s | Mean annual wind speed at 100m hub height *(primary analysis variable)* |
| `Mean_Power_Density_100m` | W/m² | Mean wind power density at 100m *(primary analysis variable)* |
| `Wind_Speed_150m` | m/s | Mean annual wind speed at 150m hub height |
| `Mean_Power_Density_150m` | W/m² | Mean wind power density at 150m |
| `Wind_Speed_200m` | m/s | Mean annual wind speed at 200m hub height |
| `Mean_Power_Density_200m` | W/m² | Mean wind power density at 200m |

## Derived Variable (computed in notebook)

| Column | Unit | Description |
|--------|------|-------------|
| `Composite_Index` | 0–1 | Normalized average of wind speed and power density at 100m. Formula: mean(min-max normalized WS_100m, min-max normalized PD_100m) |

## Notes on Data Quality
- GWA values are modeled estimates derived from mesoscale atmospheric reanalysis, not direct ground measurements.
- Values represent long-term mean annual conditions and do not reflect seasonal variability.
- Site-level conditions (terrain, roughness, obstacles) may differ from state-level averages reported here.

## Ethical Considerations
- This is a publicly available, non-sensitive environmental dataset with no personally identifiable information.
- The analysis does not account for community consent, indigenous land rights, or displacement risk — all of which are essential considerations for real-world wind project siting in Nigeria.
- Governance and equity dimensions of energy access are acknowledged as outside the scope of this technical analysis but are critical for implementation.
