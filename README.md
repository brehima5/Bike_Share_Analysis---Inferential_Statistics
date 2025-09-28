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
## III- Findings
1. **Hourly Rides: Working vs Non-Working Days**

We examined whether hourly rides differ between working and non-working days. The T-test indicated a significant difference (p = 0.000231, 95% CI [-19.29, -5.89]). This highlights predictable patterns in ridership, enabling the company to optimize operations, inventory, and marketing campaigns according to daily demand variations.

2. **Casual Riders on Holidays vs Non-Holidays**

We examined whether casual riders ride more on holidays. After performing a T-test, we found a significant difference (p = 0.0016, 95% CI [4.91, ∞]),this is a 95% confidence that the mean difference in casual riders between holidays and non-holidays is at least 4.91, with holidays being higher; meaning that casual ridership increases on holidays. This is important for the business because it suggests opportunities to design holiday-specific offers or passes, helping marketing tailor campaigns to capture casual riders when demand is highest.

3. **Registered Users During Commuting Hours**

Next, we explored whether registered users ride more during commuting hours (7–9 AM, 5–7 PM). The T-test confirmed a strong commuter pattern (p < 0.001, 95% CI [175.89, ∞]). These predictable patterns allow the operations team to optimize bike distribution and maintenance schedules, and the marketing team to design subscription plans, loyalty programs, or dynamic pricing targeting peak commuting times. This is a crucial information because it means for the company that registered riders are stable, predictable and monetizable segment.

4. **Seasonal Differences in Ridership**

We analyzed how ridership varies across seasons using one-way ANOVA with Tukey post-hoc tests. Most seasonal comparisons were statistically significant (e.g., Summer vs Winter mean difference 124.90, p < 0.001). Summer and Spring show the highest ridership, while Winter is lower. However There is not a significant difference between Spring ans Fall. Understanding these seasonal patterns helps the company plan bike allocation, seasonal promotions, and revenue forecasts, especially for attracting casual riders or tourists during low-demand periods.

5. **Weather Impact on Ridership**

We tested whether weather conditions influence average rides using one-way ANOVA. Some weather comparisons were significant (e.g., clear vs few clouds p < 0.001), while others were not. This indicates that weather can impact ridership, particularly casual riders. Operational teams can use these insights to anticipate demand fluctuations based on weather forecasts.

6. **Holidays × Rider Type Interaction**

We explored if holidays affect casual and registered riders differently using a two-way ANOVA. The interaction was highly significant (p ≈ 0), showing that holidays influence casual and registered riders in different ways. For instance, casual riders spike on holidays, whereas registered riders significantly decrease. This finding informs marketing campaigns to target casual riders with holiday promotions, and operations can allocate bikes and staff to areas favored by casual riders during holidays, This is an evidence that marketing need distinct strategies for these two segments on promotions regarding holidays.


7. **Simulated A/B Test: Feature Impact**

To assess the effect of a small app feature, we simulated an A/B test. For the primary metric (total riders), the increase post-feature was not statistically significant (p = 0.078, 95% CI [-101.26, 5.51]). For the guardrail metric (registered riders), there was no negative effect (p = 0.9936, 95% CI [-104.95, ∞]). This suggests that the feature, even without a significant improvement, does not negatively affect our chosen guardrail. In terms of practical significance and feature release, two options can be suggested: improving the feature before release, Or launching the feature to get advantage of a novelty effect, since the feature doesn't harm our other metric (guardrail).
