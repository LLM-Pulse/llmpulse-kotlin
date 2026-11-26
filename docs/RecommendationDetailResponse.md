
# RecommendationDetailResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **projectId** | **kotlin.Int** |  |  |
| **recommendationType** | [**inline**](#RecommendationType) |  |  |
| **status** | [**inline**](#Status) |  |  |
| **errorMessage** | **kotlin.String** | Set only when status is failed |  |
| **generatedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | Null until the generation completes |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **updatedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **totalRecommendations** | **kotlin.Int** |  |  |
| **highPriorityCount** | **kotlin.Int** |  |  |
| **summary** | [**RecommendationDetailResponseSummary**](RecommendationDetailResponseSummary.md) |  |  |
| **context** | [**kotlin.Any**](.md) | Generation context and run diagnostics as stored; empty until the generation completes. Its keys are not a stable contract |  |
| **reportData** | [**kotlin.collections.Map&lt;kotlin.String, kotlin.Any&gt;**](kotlin.Any.md) | The stored run, including the evidence indices (prompts_index, citations_index, own_content_index and others) that the source_refs codes of the items point to. Its keys are not a stable contract |  |
| **itemCounts** | [**RecommendationDetailResponseItemCounts**](RecommendationDetailResponseItemCounts.md) |  |  |
| **items** | [**kotlin.collections.List&lt;RecommendationItem&gt;**](RecommendationItem.md) |  |  |
| **requestId** | **kotlin.String** |  |  |


<a id="RecommendationType"></a>
## Enum: recommendation_type
| Name | Value |
| ---- | ----- |
| recommendationType | ai_visibility, social_community, brand_building, sentiment_reputation |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | pending, processing, completed, failed |



