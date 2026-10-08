
# GeoAuditRunDetail

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **sequence** | **kotlin.Int** | Run number within the audit, starting at 1 |  [optional] |
| **status** | [**inline**](#Status) |  |  [optional] |
| **trigger** | [**inline**](#Trigger) |  |  [optional] |
| **score** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **grade** | **kotlin.String** |  |  [optional] |
| **scoreDelta** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Score change against the previous completed run |  [optional] |
| **comparableToPrevious** | **kotlin.Boolean** | False when the checks or the audit settings changed since the previous run, so a diff may reflect that change |  [optional] |
| **newIssues** | **kotlin.Int** |  |  [optional] |
| **fixedIssues** | **kotlin.Int** |  |  [optional] |
| **regressedIssues** | **kotlin.Int** |  |  [optional] |
| **error** | **kotlin.String** |  |  [optional] |
| **engineVersion** | **kotlin.String** |  |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **finishedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **appUrl** | **kotlin.String** |  |  [optional] |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **metrics** | [**kotlin.collections.Map&lt;kotlin.String, java.math.BigDecimal&gt;**](java.math.BigDecimal.md) |  |  [optional] |
| **resultData** | [**kotlin.Any**](.md) | The full report of the run, in the shape of the matching technical GEO report type |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | queued, running, completed, failed, unreachable |


<a id="Trigger"></a>
## Enum: trigger
| Name | Value |
| ---- | ----- |
| trigger | scheduled, manual, api, mcp, legacy_import |



