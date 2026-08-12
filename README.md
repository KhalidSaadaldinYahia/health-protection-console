# Health Protection Console

An interactive Power BI dashboard examining whether progress in universal health coverage is matched by protection from household health costs.

## Dashboard purpose

The report combines two complementary World Bank indicators:

- **UHC service coverage index** — the reported coverage of essential health services.
- **Out-of-pocket expenditure share** — household out-of-pocket spending as a percentage of current health expenditure.

Together, these measures reveal an important policy tension: countries may expand access to services while households remain financially exposed.

## Report pages

### Protection Command

A global protection matrix comparing household cost burden with service coverage. Each point represents one country, while color identifies its analytical risk band.

### Regional Equity

Regional and income-group comparisons showing where service coverage and household financial exposure diverge.

### Country Pathways

An interactive country view for tracing changes in UHC coverage and out-of-pocket burden from 2000 to 2023, supported by a benchmark table.

### Methodology & Sources

Definitions, source information, analytical assumptions, limitations, and interpretation guardrails.

## Data

- **Source:** World Bank Open Data; underlying indicators attributed to the World Health Organization.
- **Indicators:** `SH_UHC_SCI` and `SH.XPD.OOPC.CH.ZS`
- **Coverage:** 2000–2023
- **Prepared dataset:** 4,529 complete country-year observations across 192 countries
- **Latest snapshot:** 191 countries in 2023

Source pages:

- https://data.worldbank.org/indicator/SH_UHC_SCI
- https://data.worldbank.org/indicator/SH.XPD.OOPC.CH.ZS

## How to open

1. Download `Health_Protection_Console_PBIP.zip`.
2. Extract the archive.
3. Open `HealthProtectionConsole.pbip` in Power BI Desktop.
4. If the extracted folder is moved, update the included CSV path in Power Query and refresh.

## Technical features

- Power BI Project (`.pbip`) format
- PBIR report definition
- TMDL semantic model
- Power Query CSV import
- DAX measures
- Interactive country, region, and income-group filters
- Custom healthcare financial-protection design system
- Documented sources and limitations

## Important limitations

This dashboard is descriptive and does not establish causality. Country averages are not population weighted, missing indicator-years are excluded, and national results can conceal subnational inequality. The **Protection Score** is a transparent analytical construct created for this dashboard; it is not an official WHO or World Bank indicator.

## Author

**Khalid SaadAldin Yahia**  
Data Analyst | Power BI | Python | SQL | Excel
