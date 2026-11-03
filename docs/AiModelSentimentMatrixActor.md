
# AiModelSentimentMatrixActor

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **type** | [**inline**](#Type) |  |  [optional] |
| **id** | **kotlin.Int** | Project id, or competitor id |  [optional] |
| **competitorId** | **kotlin.Int** | Null for the project, the competitor id otherwise |  [optional] |
| **name** | **kotlin.String** |  |  [optional] |
| **domain** | **kotlin.String** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. |  [optional] |
| **totalSentiments** | **kotlin.Int** | The actor&#39;s sentiment verdicts summed over the models |  [optional] |
| **models** | [**kotlin.collections.Map&lt;kotlin.String, AiModelSentimentCell&gt;**](AiModelSentimentCell.md) | One cell per model, keyed by model |  [optional] |


<a id="Type"></a>
## Enum: type
| Name | Value |
| ---- | ----- |
| type | project, competitor |



