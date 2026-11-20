
# AiModelInsightsSummaryResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **planRequiredFields** | **kotlin.collections.List&lt;kotlin.String&gt;** | The summary sections left out because they need a higher plan (brand_net_sentiment_by_model and sentiment_market_share below Growth); empty when none is |  |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **filters** | [**AiModelInsightsFiltersEcho**](AiModelInsightsFiltersEcho.md) |  |  [optional] |
| **models** | [**kotlin.collections.List&lt;AiModelInsightsModel&gt;**](AiModelInsightsModel.md) | The AI models the account has enabled or that answered in the window, in the in-app column order |  [optional] |
| **summary** | [**AiModelInsightsSummaryResponseSummary**](AiModelInsightsSummaryResponseSummary.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



