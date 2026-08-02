
# CreateWebhookRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **eventType** | [**inline**](#EventType) |  |  |
| **targetUrl** | **kotlin.String** | Public HTTPS URL that will receive signed event payloads |  |


<a id="EventType"></a>
## Enum: event_type
| Name | Value |
| ---- | ----- |
| eventType | mention.created, competitor_mention.created, citation.created, prompt_execution.completed, sentiment.negative_detected, recommendation.completed, intelligence_task.completed |



