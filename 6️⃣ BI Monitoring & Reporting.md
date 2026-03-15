🎯 Goal
Ensure failures are visible, not silent. 

```SQL
SELECT
    NAME,
    STATE,
    ERROR_MESSAGE,
    COMPLETED_TIME
FROM ACCOUNT_USAGE.TASK_HISTORY
WHERE STATE != 'SUCCEEDED';
```
This query runs daily and retrieves all errors attributed to Snowflake tasks 
and uploaded into a Snowflake Monitoring Dashbaord into our Power BI CRM App.

Conclusion:
* Monitoring built into the platform
* Failures surfaced to BI tools
* Ops transparency for stakeholders
