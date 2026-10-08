
# GeoAuditResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.String** | Stable audit id |  [optional] |
| **auditType** | [**inline**](#AuditType) |  |  [optional] |
| **target** | **kotlin.String** | The audited domain (site-wide types) or page URL, normalized |  [optional] |
| **countryCode** | **kotlin.String** |  |  [optional] |
| **cadence** | [**inline**](#Cadence) |  |  [optional] |
| **status** | [**inline**](#Status) |  |  [optional] |
| **pausedReason** | **kotlin.String** | user, or unreachable when three runs in a row could not reach the site |  [optional] |
| **schedule** | [**GeoAuditSchedule**](GeoAuditSchedule.md) |  |  [optional] |
| **nextRunAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **emailAlerts** | **kotlin.Boolean** |  |  [optional] |
| **recurringAvailable** | **kotlin.Boolean** | Whether this audit type can run weekly or monthly |  [optional] |
| **checksTracked** | **kotlin.Boolean** | Whether runs of this type produce findings and issues, or a score only |  [optional] |
| **latestRun** | [**GeoAuditRun**](GeoAuditRun.md) |  |  [optional] |
| **openIssues** | **kotlin.Int** |  |  [optional] |
| **openCriticalIssues** | **kotlin.Int** |  |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **appUrl** | **kotlin.String** |  |  [optional] |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |


<a id="AuditType"></a>
## Enum: audit_type
| Name | Value |
| ---- | ----- |
| auditType | agent_readiness, robots_txt, crawlability, schema, content_readiness, discoverability, site_structure |


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



