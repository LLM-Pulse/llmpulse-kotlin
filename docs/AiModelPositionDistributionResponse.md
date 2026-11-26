
# AiModelPositionDistributionResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **filters** | [**AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  |  |
| **granularity** | [**inline**](#Granularity) |  |  |
| **brands** | [**kotlin.collections.List&lt;AiModelPositionDistributionBrand&gt;**](AiModelPositionDistributionBrand.md) | The first brand (brand1, else the project) and the second (brand2, else the competitor with the most mentions, else the project), each left out when it has no mention in the window |  |
| **maxStackedValue** | **kotlin.Int** | The largest mentions count of one period across the brands, for a shared chart axis |  |
| **requestId** | **kotlin.String** |  |  |


<a id="Granularity"></a>
## Enum: granularity
| Name | Value |
| ---- | ----- |
| granularity | day, week, month |



