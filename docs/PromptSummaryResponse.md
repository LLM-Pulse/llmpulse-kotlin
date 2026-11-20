
# PromptSummaryResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **planRequiredFields** | **kotlin.collections.List&lt;kotlin.String&gt;** | The row fields left out because they need a higher plan (the sentiment fields below Growth); empty when none is |  |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **filters** | [**MetricsFiltersEcho**](MetricsFiltersEcho.md) |  |  [optional] |
| **breakdown** | **kotlin.String** |  |  [optional] |
| **sort** | **kotlin.String** |  |  [optional] |
| **sortDir** | **kotlin.String** |  |  [optional] |
| **page** | **kotlin.Int** |  |  [optional] |
| **perPage** | **kotlin.Int** |  |  [optional] |
| **total** | **kotlin.Int** |  |  [optional] |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;PromptSummaryRow&gt;**](PromptSummaryRow.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



