
# AiModelWeightedVisibilityMatrixActor

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **type** | [**inline**](#Type) |  |  [optional] |
| **id** | **kotlin.Int** | Project id, or competitor id |  [optional] |
| **competitorId** | **kotlin.Int** | Null for the project, the competitor id otherwise |  [optional] |
| **name** | **kotlin.String** |  |  [optional] |
| **domain** | **kotlin.String** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. |  [optional] |
| **totalWeightedVisibilityScore** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | The actor&#39;s AI Visibility Score across the enabled models, its points there divided by the project&#39;s days with answers in them, so actors compare |  [optional] |
| **models** | [**kotlin.collections.Map&lt;kotlin.String, AiModelWeightedVisibilityCell&gt;**](AiModelWeightedVisibilityCell.md) | One cell per model, keyed by model |  [optional] |


<a id="Type"></a>
## Enum: type
| Name | Value |
| ---- | ----- |
| type | project, competitor |



