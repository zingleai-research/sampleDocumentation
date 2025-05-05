# Data Asset: prd_dw.fact.engagement_cohorts.t11

## Definition
Binary indicator (1=yes, 0=no) showing whether a user performed any cutting activity 10 months prior to the current evaluation month. Part of a t1-t12 series tracking user engagement patterns over time.

## Calculation Method
Calculated using the LAG function that looks back 10 months in the user's activity timeline, partitioned by user_id and ordered chronologically by month.

### Upstream Dependencies
1. **prd_dw.fact.cut_session_master.project_id**
   - Identifies cutting activities by linking sessions to specific design projects, providing the foundational data to determine monthly user cutting activity

2. **prd_dw.dim.user_profile.user_id**
   - Serves as the partitioning key in the LAG function to ensure time-lagged indicators are calculated separately for each individual user

3. **dw.dim.date.first_day_of_month**
   - Establishes the chronological sequence for the ORDER BY clause, allowing accurate 10-month lookback from evaluation month

## Usage
Enables longitudinal analysis of user behavior, retention tracking, and cohort analysis. Used in predictive models for user churn, engagement forecasting, and identifying patterns in activity cycles.

### Downstream Dependencies
None currently identified.
