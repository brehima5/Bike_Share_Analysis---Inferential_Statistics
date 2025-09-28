# Bike_Share_Analysis---Inferential_Statistics

*Academic project analyzing a bike-share dataset using Python and Tableau. Applies statistical methods and an A/B test to explore real-world business scenarios, uncover patterns, and generate actionable insights.*

---------------------------------
## I- Business Framing & Context
This project is centered on a **bike-share company** seeking to gain a deeper understanding of its riders’ behavior over a two-year period (2011–2012), based on an hourly dataset. The business context is to identify when, where, and how ridership patterns shift across user types (casual vs. registered), time windows (commuting vs. leisure hours), and external conditions (holidays, weather, and seasons).

The company’s stakeholders are interested in insights that support both operational and strategic decisions:
- **Product Management:** When/where demand is strong or fragile; user behavior patterns; which hypotheses to prioritize next quarter
- **Operations:** anticipating ridership peaks for inventory rebalancing, staffing, and maintenance scheduling.
- **Marketing:** optimizing promotions by targeting time periods, seasons, and user segments likely to respond.
- **Policy & Ethics:** Equity of access; avoiding decisions that disadvantage specific times/areas; responsible communication of uncertainty.

To address these needs, the project applies **inferential statistics, hypothesis testing, and an A/B testing experiment** to evaluate real-world scenarios. The results are visualized in Python and Tableau, turning raw ridership data into actionable insights for business decision-making.

## II- Methods Summary
1. **Data Cleaning**:
+ Correcting data types for columns : dteday, season, year, holiday, weekday, workingday, weathersit
+ Data quality check: count of hour for each day, check missing values, ensuring each year has 12 months.
  
2. **Exploratory Data Analysis (EDA)**:
trends across time, season, holidays, weather, rider type using tableau visuals.
3. **Hypothesis Testing**:
T-tests, welch's T-test, ANOVA, two-way ANOVA, Sampling techniques computing P-values, confidence intervals, decisions and practical significance.
4. **A/B Testing:**
  - Primary metric: average houly riders pre/post-feature on working days and specific weather conditions
  - Guardrail metric: average registered riders pre/post-feature.
