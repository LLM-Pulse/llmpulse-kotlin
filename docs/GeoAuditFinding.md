
# GeoAuditFinding

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **checkKey** | **kotlin.String** | Stable key of the check within its audit type |  [optional] |
| **checkTitle** | **kotlin.String** |  |  [optional] |
| **subjectKey** | **kotlin.String** | What the check is about (site for site-wide checks, a bot slug for robots.txt bot checks) |  [optional] |
| **subject** | **kotlin.String** |  |  [optional] |
| **status** | [**inline**](#Status) |  |  [optional] |
| **severity** | [**inline**](#Severity) |  |  [optional] |
| **evidence** | [**kotlin.Any**](.md) |  |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | pass, warn, fail, info, not_applicable, unknown |


<a id="Severity"></a>
## Enum: severity
| Name | Value |
| ---- | ----- |
| severity | critical, high, medium, low, info |



