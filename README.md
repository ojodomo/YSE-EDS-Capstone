# GIS-Based Site Suitability Analysis for Wind Energy Development in Nigeria

**Yale School of the Environment — Environmental Data Science Certificate Program**
**Student:** Odiniya Ojodomo | **Submitted:** March 2026

---

## 📌 50-Word Summary

This project identifies optimal sites for utility-scale wind energy across Nigeria's 37 states using Global Wind Atlas data. Wind speed and power density at 100m were combined into a composite suitability index. Plateau, Gombe, and Adamawa ranked highest, making North East and North West Nigeria priority corridors for wind investment.

---

## 🔬 Project Question

**Which Nigerian states and regions offer the highest suitability for utility-scale wind energy development, based on a composite index of wind speed and wind power density at 100m hub height?**

Nigeria faces a persistent electricity crisis, with over 85 million people lacking reliable access to electricity. Despite substantial wind resources, especially in the northern states, wind energy remains critically underutilised. A key barrier is the lack of data-driven, multi-variable site-selection frameworks. This project addresses that gap.

---

## 🗂️ Repository Structure

```
nigeria-wind-suitability/
│
├── README.md                          ← You are here
│
├── data/
│   ├── raw/
│   │   └── 20260130_GWA.csv           ← Raw Global Wind Atlas dataset (37 Nigerian states)
│   └── README_data.md                 ← Data dictionary and provenance
│
├── notebooks/
│   └── wind_suitability_analysis.Rmd  ← Main analysis notebook (R Markdown)
│
├── communication/
│   ├── viz1_state_ranking.png         ← Ranked dot plot: wind speed by state
│   ├── viz2_regional_boxplot.png      ← Box plot: regional wind speed comparison
│   ├── viz3_histogram.png             ← Histogram: distribution of wind speeds
│   └── key_findings_slide.pptx        ← Summary slide deck
│
└── LICENSE.md
```

---

## 📊 Data Sources

| Dataset | Source | Description |
|---------|--------|-------------|
| Global Wind Atlas (GWA) | [globalwindatlas.info](https://globalwindatlas.info) | Wind speed (m/s) and mean power density (W/m²) at 10m, 50m, 100m, 150m, 200m hub heights for all 37 Nigerian states |

- **Access date:** January 30, 2026
- **Coverage:** All 36 Nigerian states + Federal Capital Territory (FCT)
- **Variables used:** Wind speed at 100m (m/s), Mean Power Density at 100m (W/m²)

### Data Dictionary

| Variable | Unit | Description |
|----------|------|-------------|
| `Wind_Speed_100m` | m/s | Mean annual wind speed at 100m hub height |
| `Mean_Power_Density_100m` | W/m² | Mean wind power density at 100m hub height |
| `Region` | — | Nigeria's 6 geopolitical regions |
| `Composite_Index` | 0–1 | Normalized composite score (wind speed + power density) |

### Ethical Considerations
- Dataset is publicly available and does not contain personally identifiable information.
- GWA data reflects modeled wind resource estimates; site-level variation and land-use constraints are acknowledged as limitations.
- Analysis does not incorporate community consent or land rights data — these are critical for real-world deployment planning and are noted as necessary next steps.

---

## 🔑 Key Findings

1. **Northern Nigeria dominates**: North East and North West regions record the highest wind speeds and power densities at 100m hub height.
2. **Top 5 states by composite index**: Plateau (0.999), Gombe (0.991), Adamawa (0.918), Borno (0.867), Zamfara (0.853).
3. **5 states exceed 7.0 m/s** at 100m — the threshold commonly cited for viable utility-scale wind development.
4. **Southern regions** (South South, South East) average below 5.0 m/s — better suited to hybrid or distributed energy systems.
5. **Composite indexing matters**: Ranking by wind speed alone vs. wind speed + power density produces meaningfully different prioritizations due to air density effects.

---

## ⚙️ How to Reproduce

### Requirements
- R (version ≥ 4.0)
- R packages: `tidyverse`, `ggplot2`, `dplyr`, `knitr`, `rmarkdown`

### Steps
```r
# Install required packages
install.packages(c("tidyverse", "ggplot2", "dplyr", "knitr", "rmarkdown"))

# Open and knit the notebook
rmarkdown::render("notebooks/wind_suitability_analysis.Rmd")
```

The notebook loads `data/raw/20260130_GWA.csv` directly — no additional setup required.

---

## ⚠️ Limitations

- Analysis relies on modeled GWA data, not site-measured wind records
- Land use, protected areas, grid proximity, and road access are not incorporated in this version
- Power density values are mean annual estimates and do not reflect seasonal or diurnal variability
- A full GIS suitability model would additionally weight terrain, exclusion zones, and proximity to demand centres

---

*Yale School of the Environment | Environmental Data Science Certificate | 2025–2026*
