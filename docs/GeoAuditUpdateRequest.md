
# GeoAuditUpdateRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **cadence** | [**inline**](#Cadence) |  |  [optional] |
| **scheduleDay** | **kotlin.Int** | Weekly: 0 (Sunday) to 6. Monthly: 1 to 28. |  [optional] |
| **scheduleHour** | **kotlin.Int** | Hour of the day, 0 to 23, in the audit time zone |  [optional] |
| **status** | [**inline**](#Status) | paused stops scheduled runs, active resumes them, archived is the same as DELETE |  [optional] |
| **emailAlerts** | **kotlin.Boolean** |  |  [optional] |


<a id="Cadence"></a>
## Enum: cadence
| Name | Value |
| ---- | ----- |
| cadence | once, weekly, monthly |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | active, paused, archived |



