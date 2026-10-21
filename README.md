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

## Risk-band rules

- **More protected:** UHC ≥ 60 and OOP < 40
- **High cost:** UHC ≥ 60 and OOP ≥ 40
- **Coverage gap:** UHC < 60 and OOP < 40
- **Critical:** UHC < 60 and OOP ≥ 40

These cutoffs are transparent portfolio rules, not official World Bank or WHO classifications.


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

## Open and inspect the report

- [Preview the dashboard PDF](Health_Protection_Console_Dashboard.pdf). A PDF is a static export; the `.pbip` project contains the interactive report.
- [Browse the Power BI project](project/) or [download this repository as a ZIP](https://github.com/KhalidSaadaldinYahia/health-protection-console/archive/refs/heads/main.zip). Keep the `project` folder intact after extracting.
- Open [`HealthProtectionConsole.pbip`](project/HealthProtectionConsole.pbip) from the extracted `project` folder in a recent Power BI Desktop. The `.pbip` file references its sibling `.Report` and `.SemanticModel` folders; it cannot open by itself after downloading only that file.
- On refresh, choose **Anonymous** access if Power BI requests credentials for `raw.githubusercontent.com`. The project reads the included CSV snapshot from this repository's public `main` branch. For offline refresh, replace each table query's `Web.Contents(...)` CSV source with `File.Contents(...)` pointing to its included local `project/data` CSV.

The CSV data snapshots are included under [`project/data`](project/data/). A `.pbix` was not generated because the PBIP source cannot be converted faithfully without opening and saving it in Power BI Desktop.
