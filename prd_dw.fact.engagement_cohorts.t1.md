# Data Asset: prd_dw.fact.engagement_cohorts.t1

## Definition
Binary indicator (0 or 1) that tracks whether a user performed any cutting activity during the current evaluation month. A value of 1 indicates the user cut at least one project, while 0 indicates no cutting activity.

## Calculation Method
Determined by checking if a user has at least one associated project_id in the cut_session_master table during the current evaluation month. This serves as a fundamental metric for user engagement classification and cohort analysis.

### Upstream Dependencies
1. **prd_dw.fact.cut_session_master.project_id**
   - Provides unique identifiers linking cutting sessions to specific design projects. The presence of project_id values for a user in the current month determines the binary value of t1.

## Usage
Used in engagement analysis to segment users based on cutting behavior, track month-over-month changes in activity, and identify patterns in user engagement. Likely contributes to dashboards monitoring user activity and retention, and supports cohort analyses to understand relationships between cutting behavior and other user actions.

### Downstream Dependencies
None currently identified.
