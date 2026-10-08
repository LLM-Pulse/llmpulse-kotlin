
# GeoAuditCreateRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **target** | **kotlin.String** | The domain (site-wide types) or page URL to audit |  |
| **auditTypes** | [**inline**](#kotlin.collections.List&lt;AuditTypes&gt;) | One or more audit types; each becomes its own audit and starts its first run |  |
| **cadence** | [**inline**](#Cadence) | once (default), weekly or monthly. Weekly and monthly need a type whose checks are tracked and count against the plan limit of recurring audits |  [optional] |


<a id="kotlin.collections.List<AuditTypes>"></a>
## Enum: audit_types
| Name | Value |
| ---- | ----- |
| auditTypes | agent_readiness, robots_txt, crawlability, schema, content_readiness, discoverability, site_structure |


<a id="Cadence"></a>
## Enum: cadence
| Name | Value |
| ---- | ----- |
| cadence | once, weekly, monthly |



