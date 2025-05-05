# Data Asset: prd_dw.fact.udm_registrations_atheja_testing.evaluation_date

## Definition
Calendar date (without time) when a user registered a machine to their account. Business users may also refer to this field as 'registration_date'.

## Calculation Method
Derived directly from prd_dw.fact.machine_registration.registration_date by removing the time component, focusing solely on the date portion to support date-level analysis.

### Upstream Dependencies
1. **prd_dw.fact.machine_registration.registration_date**
   - Provides the original timestamp (date and time) of when a user registered a machine to their account. This timestamp is cast to a date type (::date) to create the evaluation_date.

## Usage
Used for daily-level analysis of user registration patterns and machine engagement metrics, allowing for date-based evaluation of registration activities.

### Downstream Dependencies
None currently identified.
