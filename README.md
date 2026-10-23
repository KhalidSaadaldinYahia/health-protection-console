# Health Protection Console

## Files

- [Open the Power BI dashboard](HealthProtectionConsole.pbix) in Power BI Desktop.
- [Read the PDF analytical preview](Health_Protection_Console_Dashboard.pdf). This PDF summarises independently checked figures; it is not yet a page-for-page export of the PBIX. A matching PDF export is pending verification in Power BI Desktop.

The PBIX is the single-file dashboard. A data refresh may need network access to its saved source URLs.

## Dashboard purpose

The report combines two complementary World Bank indicators:

- **UHC service coverage index** — the reported coverage of essential health services.
- **Out-of-pocket expenditure share** — household out-of-pocket spending as a percentage of current health expenditure.

These indicators describe service coverage and the financing mix. The out-of-pocket share is **not** a measure of the percentage of households in hardship or of financial protection. Household hardship requires a separate indicator, such as catastrophic or impoverishing health expenditure.

## Report pages

### Coverage & Spending

A matrix comparing the out-of-pocket share of health spending with service coverage. Each point represents one country; color identifies its indicator quadrant.

### Regional Comparison

Regional and income-group comparisons of service coverage and out-of-pocket financing share.

### Country Pathways

An interactive country view for tracing changes in UHC coverage and out-of-pocket financing share from 2000 to 2023, supported by a benchmark table.

### Methodology & Sources

Definitions, source information, analytical assumptions, limitations, and interpretation guardrails.

## Data

- **Source:** World Bank Open Data; underlying indicators attributed to the World Health Organization.
- **Indicators:** `SH_UHC_SCI` and `SH.XPD.OOPC.CH.ZS`
- **Coverage:** 2000–2023
- **Prepared dataset:** 4,529 complete country-year observations across 192 countries
- **Latest snapshot:** 191 countries in 2023

The prepared data used for the PBIX is the analytical snapshot. It is a country-year inner join of available values for both indicators, excluding years missing either value. Region and income group are contextual labels in the prepared file. The exact original API request URLs, extraction date, and transformation script were not retained, so the source pages identify the indicators but cannot reproduce the exact historical snapshot byte for byte.

Source pages:

- https://data.worldbank.org/indicator/SH_UHC_SCI
- https://data.worldbank.org/indicator/SH.XPD.OOPC.CH.ZS

## Indicator quadrants

- **Higher UHC / lower OOP share:** UHC ≥ 60 and OOP < 40
- **Higher UHC / higher OOP share:** UHC ≥ 60 and OOP ≥ 40
- **Lower UHC / lower OOP share:** UHC < 60 and OOP < 40
- **Lower UHC / higher OOP share:** UHC < 60 and OOP ≥ 40

These cutoffs are descriptive portfolio rules, not official World Bank or WHO classifications. “Higher” and “lower” describe the two indicators only; they do not classify household hardship.


## Technical features

- Power BI Desktop (`.pbix`) report and semantic model
- PBIR report definition
- TMDL semantic model
- Power Query CSV import
- DAX measures
- Interactive country, region, and income-group filters
- Custom healthcare indicator design system
- Documented sources and limitations

## Important limitations

This dashboard is descriptive and does not establish causality. Country averages are not population weighted, missing indicator-years are excluded, and national results can conceal subnational inequality. The arithmetic `UHC index − OOP share` compares quantities with different definitions and is **not** a validated financial-protection score. Its numeric value must not be interpreted as household hardship, an outcome, or a policy target. The internal model retains its legacy measure and column identifiers to preserve report bindings; interactive chart labels identify the arithmetic UHC-minus-OOP comparison as exploratory. It is a difference of unlike indicators, not a protection outcome.

## Author

**Khalid SaadAldin Yahia**  
Data Analyst | Power BI | Python | SQL | Excel
