# SOLAR-GENERATION-AND-ELEC-USAGE-GENERATION-ANALYSIS



**Objective:**

The goal of this project is to develop and document an analytical model for evaluating the cost savings and viability of installing a battery system to store excess solar electricity in a household.

**Data Understanding:**
- The dataset used includes historical data from the year 2020, containing information about solar energy generation and electrical usage per hour.
- The dataset consists of 8,760 rows and 3 columns.

**Data Checks:**
- The dataset was thoroughly checked for duplicate and null values, and none were found.
- Outliers in the energy usage column were identified and removed from the dataset. These outliers were dropped because an electrical usage of 46,000 kWh was significantly higher than the rest of the dataset, and negative values for electrical usage were scientifically improbable in relation to electricity.

**Model Purpose:**
- The primary purpose of the model is to predict annual cost savings over a twenty-year period.
- For this purpose, the model utilizes Facebook Prophet (FB Prophet).

**Methodology and Plan of Approach:**
- The model data frame was grouped by month and the battery level columns, as the savings depend on the battery level multiplied by the cost of purchased electricity.
- The logic behind this approach is that whenever the battery level is not zero, it signifies electricity purchased forgone, resulting in cost savings (foregone cost).

**Calculations and Feature Engineering:**
- Month and year were extracted from the date-time column.
- The new column was then grouped to calculate the summation of battery level throughout the month.
- The new battery level forecasted over a twenty-year period was used to calculate cost savings for different scenarios.
- Compounded cost was calculated and multiplied by the battery level to determine annual cost savings.
- Net Present Value (NPV) was calculated based on the new cost-saving figures in both scenarios.
- Internal Rate of Return (IRR) was generated using the new columns.

**Assumptions Made:**
- The discounting rate remained constant throughout the twenty-year period.
- No external factors, except for seasonality, affected the dataset. This includes changes in electrical appliances, family size, global warming, damages, repairs, and maintenance, which were assumed to have no impact on solar energy generation or electrical usage. The dataset, apart from the outliers, is considered accurate or contains minimal errors.
