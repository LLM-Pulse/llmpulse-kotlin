
# ListWebhooks200ResponseDataInner

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  [optional] |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **eventType** | [**inline**](#EventType) |  |  [optional] |
| **targetUrl** | **kotlin.String** | The URL deliveries are sent to. A read-only API key receives only its scheme, host and any non-default port followed by &#x60;/…&#x60; (for example &#x60;https://hook.eu1.make.com/…&#x60;); a &#x60;read_write&#x60; scope key receives the full URL. |  [optional] |
| **disabled** | **kotlin.Boolean** | True when the subscription receives no more events, including when the API key or OAuth connection that created it was revoked, or when that API key is limited to some projects and no longer covers the subscription&#39;s project. Creating it again with the same project, event and URL replaces it with a new subscription and secret. |  [optional] |
| **failureCount** | **kotlin.Int** |  |  [optional] |
| **lastDeliveredAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |


<a id="EventType"></a>
## Enum: event_type
| Name | Value |
| ---- | ----- |
| eventType | mention.created, competitor_mention.created, citation.created, prompt_execution.completed, sentiment.negative_detected, recommendation.completed, intelligence_task.completed, intelligence_task.updated, geo_audit_run.completed, geo_audit_alert.triggered |



