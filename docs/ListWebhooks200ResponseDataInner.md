
# ListWebhooks200ResponseDataInner

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  [optional] |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **eventType** | [**inline**](#EventType) |  |  [optional] |
| **targetUrl** | **kotlin.String** |  |  [optional] |
| **disabled** | **kotlin.Boolean** |  |  [optional] |
| **failureCount** | **kotlin.Int** |  |  [optional] |
| **lastDeliveredAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |


<a id="EventType"></a>
## Enum: event_type
| Name | Value |
| ---- | ----- |
| eventType | mention.created, competitor_mention.created, citation.created, prompt_execution.completed, sentiment.negative_detected, recommendation.completed, intelligence_task.completed |



