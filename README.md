# Bike_Share_Analysis---Inferential_Statistics

*Academic project analyzing a bike-share dataset using Python and Tableau. Applies statistical methods and an A/B test to explore real-world business scenarios, uncover patterns, and generate actionable insights.*

---------------------------------
## I- BUSINESS FRAMING & CONTEXT
This project is centered on a **bike-share company** seeking to gain a deeper understanding of its riders’ behavior over a two-year period (2011–2012), based on an hourly dataset. The business context is to identify when, where, and how ridership patterns shift across user types (casual vs. registered), time windows (commuting vs. leisure hours), and external conditions (holidays, weather, and seasons).

The company’s stakeholders are interested in insights that support both operational and strategic decisions:
- **Product Management:** When/where demand is strong or fragile; user behavior patterns; which hypotheses to prioritize next quarter
- **Operations:** anticipating ridership peaks for inventory rebalancing, staffing, and maintenance scheduling.
- **Marketing:** optimizing promotions by targeting time periods, seasons, and user segments likely to respond.
- **Policy & Ethics:** Equity of access; avoiding decisions that disadvantage specific times/areas; responsible communication of uncertainty.

To address these needs, the project applies **inferential statistics, hypothesis testing, and an A/B testing experiment** to evaluate real-world scenarios. The results are visualized in Python and Tableau, turning raw ridership data into actionable insights for business decision-making.

## II- METHODS SUMMARY
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
## III- FINDINGS
1. **Hourly Rides: Working vs Non-Working Days**

We examined whether hourly rides differ between working and non-working days. The T-test indicated a significant difference (p = 0.000231, 95% CI [-19.29, -5.89]). This highlights predictable patterns in ridership, enabling the company to optimize operations, inventory, and marketing campaigns according to daily demand variations.

<img width="1184" height="484" alt="working days vs non workday" src="https://github.com/user-attachments/assets/f3494019-3d5f-49af-9620-71da951c5ba7" />


*t_distribution of hourly average ride on working days & average ridership on workingday vs non_working day*


2. **Casual Riders on Holidays vs Non-Holidays**

We examined whether casual riders ride more on holidays. After performing a T-test, we found a significant difference (p = 0.0016, 95% CI [4.91, ∞]),this is a 95% confidence that the mean difference in casual riders between holidays and non-holidays is at least 4.91, with holidays being higher; meaning that casual ridership increases on holidays. This is important for the business because it suggests opportunities to design holiday-specific offers or passes, helping marketing tailor campaigns to capture casual riders when demand is highest.

<img width="1183" height="484" alt="holiday vs non holiday" src="https://github.com/user-attachments/assets/09f69b66-1bad-462a-8e2a-9b3d9a0603c8" />


3. **Registered Users During Commuting Hours**

Next, we explored whether registered users ride more during commuting hours (7–9 AM, 5–7 PM). The T-test confirmed a strong commuter pattern (p < 0.001, 95% CI [175.89, ∞]). These predictable patterns allow the operations team to optimize bike distribution and maintenance schedules, and the marketing team to design subscription plans, loyalty programs, or dynamic pricing targeting peak commuting times. This is a crucial information because it means for the company that registered riders are stable, predictable and monetizable segment.

<img width="1229" height="490" alt="commut vs not commute" src="https://github.com/user-attachments/assets/bd675516-f0df-494e-ace7-00e2094a9bf8" />


4. **Seasonal Differences in Ridership**

We analyzed how ridership varies across seasons using one-way ANOVA with Tukey post-hoc tests. Most seasonal comparisons were statistically significant (e.g., Summer vs Winter mean difference 124.90, p < 0.001). Summer and Spring show the highest ridership, while Winter is lower. However There is not a significant difference between Spring ans Fall. Understanding these seasonal patterns helps the company plan bike allocation, seasonal promotions, and revenue forecasts, especially for attracting casual riders or tourists during low-demand periods.

<img width="854" height="550" alt="seasonal" src="https://github.com/user-attachments/assets/3322ee30-3fe3-42de-8d32-39476ce6fb2f" />



5. **Weather Impact on Ridership**

We tested whether weather conditions influence average rides using one-way ANOVA. Some weather comparisons were significant (e.g., clear vs few clouds p < 0.001), while others were not. This indicates that weather can impact ridership, particularly casual riders. Operational teams can use these insights to anticipate demand fluctuations based on weather forecasts.

<img width="871" height="627" alt="Screenshot 2025-09-28 at 2 15 05 PM" src="https://github.com/user-attachments/assets/98def8cf-2972-42e7-a17b-e96f650ded41" />


6. **Holidays × Rider Type Interaction**

We explored if holidays affect casual and registered riders differently using a two-way ANOVA. The interaction was highly significant (p ≈ 0), showing that holidays influence casual and registered riders in different ways. For instance, casual riders spike on holidays, whereas registered riders significantly decrease. This finding informs marketing campaigns to target casual riders with holiday promotions, and operations can allocate bikes and staff to areas favored by casual riders during holidays, This is an evidence that marketing need distinct strategies for these two segments on promotions regarding holidays.

<img width="845" height="541" alt="interaction" src="https://github.com/user-attachments/assets/bc7029ea-a16c-4b12-9e60-3354cda8a3ac" />


7. **Simulated A/B Test: Feature Impact**

To assess the effect of a small app feature, we simulated an A/B test. For the primary metric (total riders), the increase post-feature was not statistically significant (p = 0.078, 95% CI [-101.26, 5.51]). For the guardrail metric (registered riders), there was no negative effect (p = 0.9936, 95% CI [-104.95, ∞]). This suggests that the feature, even without a significant improvement, does not negatively affect our chosen guardrail. In terms of practical significance and feature release, two options can be suggested: improving the feature before release, or launching the feature to get advantage of a novelty effect, since the feature doesn't harm our other metric (guardrail)
**Implication:** Feature is safe but not driving meaningful growth.

<img width="1184" height="484" alt="primary metric" src="https://github.com/user-attachments/assets/5d8667a2-3950-4b2a-b1d0-4fa51e62bbe9" />

*primary metric*


<img width="1184" height="484" alt="guardrail" src="https://github.com/user-attachments/assets/4f8e66be-236e-492a-808f-c44bdd28cd95" />

*Guardrail metric*

## IV- RECOMMENDATIONS:
**Product manager and Marketing team:** 

  - Launch "Holiday Explorer Pass" targeting casual users with day passes on tourist-friendly routes
  - Implement weekly fare caps for registered riders like the MTA *New york city metro system* (free rides after certain threshold)
  - Aggressive acquisition campaigns in Fall, to maintain ridership as long as possible before Winter, which is the lowest ridership season.

**Operations Lead**

  - Morning peaks: Concentrate bikes in residential areas
  - Dynamic Bike Redistribution
  - Holidays: Focus on tourist areas and recreational routes
  - Increase availability during "clear" and "few clouds" conditions (highest demand)
  - Develop "Weather Guarantee" promotions for rainy days
  - Implement dynamic pricing that rewards riding in less-than-ideal conditions
  - Schedule major maintenance during low-demand periods identified in seasonal analysis

**Policy & Ethics Advisor**

  - Maintain offline registration options for elderly and low-digital-literacy users
  - Dynamic pricing and bike redistribution could disadvantage certain neighborhoods, so conducting regular equity audits of bike availability across neighborhoods is crucial for ethics     and equity purposes.
  - Registered commuters demonstrate high dependency on service for essential transportation, so implementing the weekly fare cap to protect frequent low income commuters.

## V- Ethics & limitations

Overall, the dataset was very clean. a few things limitations are :
- 78 days of the data had less than 24hours, 8 with less than 22 hours: it is a small percentage, so we didn't take action for it.
- Comparing the means of certain varibales needed a particular approach than just using the appropriate statistical method: this is the case for working days vs non working days where we used a sampling technique to balance the samples sizes before running the test. 

