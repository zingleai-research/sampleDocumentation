# Data Asset: prd_dw.fact.engagement_cohorts.days_cut_this_month

## Definition
The total number of days in a month where a user performed at least one cutting activity (had at least one project cut), regardless of how many projects were cut on that day.

## Calculation Method
Counts each unique day where a user has at least one project cut, using project IDs from cutting sessions. Each day with cutting activity counts as 1, regardless of the number of different projects cut that day.

### Upstream Dependencies
1. **prd_dw.fact.cut_session_master.project_id**
   - Serves as a unique identifier linking cutting sessions to specific design projects, enabling the system to identify when a user has performed a cutting activity on a given day

## Usage
Key engagement indicator used to classify users into engagement categories, with users who cut on 5+ days in a month being categorized as 'Monthly Power' users. Enables analysis of user engagement frequency and consistency across different time periods.

### Downstream Dependencies
1. **prd_dw.fact.engagement_cohorts.prev_days_cut_this_month**
   - Directly mapped to represent the previous month's cutting activity days

2. **prd_dw.stage.tbl_temp_user_status_in_previous_month.monthly_classification**
   - Used with a threshold of 5+ days to identify 'Monthly Power' users versus regular 'Monthly' users in the previous month

3. **prd_dw.stage.tbl_temp_user_status_in_previous_quarter.monthly_classification**
   - Used with a threshold of 5+ days to identify 'Monthly Power' users versus regular 'Monthly' users in the previous quarter

4. **analytics.user_subscription_engagement_by_month.days_cut_prev_month**
   - Directly mapped with NULL handling to represent previous month's cutting days, defaulting to 0 if no data exists

5. **analytics.user_subscription_engagement_by_month.engagement_classification**
   - Contributes to the monthly_classification that determines the user's current engagement category

6. **analytics.user_subscription_engagement_by_month.engagement_classification_12m**
   - Contributes to user classification 12 months after the evaluation month

7. **analytics.user_subscription_engagement_by_month.engagement_classification_3m**
   - Contributes to user classification 3 months after the evaluation month

8. **analytics.user_subscription_engagement_by_month.engagement_classification_6m**
   - Contributes to user classification 6 months after the evaluation month

9. **analytics.user_subscription_engagement_by_month.month_end_engagement_classification**
   - Contributes to user classification at the end of each month
