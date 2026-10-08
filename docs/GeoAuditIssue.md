
# GeoAuditIssue

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  [optional] |
| **checkKey** | **kotlin.String** |  |  [optional] |
| **checkTitle** | **kotlin.String** |  |  [optional] |
| **subjectKey** | **kotlin.String** |  |  [optional] |
| **subject** | **kotlin.String** |  |  [optional] |
| **severity** | **kotlin.String** |  |  [optional] |
| **state** | [**inline**](#State) |  |  [optional] |
| **badge** | [**inline**](#Badge) | How the latest comparable run moved the issue |  [optional] |
| **accepted** | **kotlin.Boolean** |  |  [optional] |
| **acceptedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **regressionCount** | **kotlin.Int** |  |  [optional] |
| **evidence** | [**kotlin.Any**](.md) |  |  [optional] |
| **updatedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |


<a id="State"></a>
## Enum: state
| Name | Value |
| ---- | ----- |
| state | open, fixed, gone |


<a id="Badge"></a>
## Enum: badge
| Name | Value |
| ---- | ----- |
| badge | new, persisting, regressed, fixed, gone |



