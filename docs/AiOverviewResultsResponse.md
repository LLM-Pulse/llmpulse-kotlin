
# AiOverviewResultsResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **filters** | [**AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  |  |
| **granularity** | [**inline**](#Granularity) |  |  |
| **summary** | [**AiOverviewResultCounts**](AiOverviewResultCounts.md) |  |  |
| **chart** | [**kotlin.collections.List&lt;AiOverviewResultsResponseChartInner&gt;**](AiOverviewResultsResponseChartInner.md) | One point per period of the window, oldest first, 0 included |  |
| **byPrompt** | [**AiOverviewResultsResponseByPrompt**](AiOverviewResultsResponseByPrompt.md) |  |  |
| **requestId** | **kotlin.String** |  |  |


<a id="Granularity"></a>
## Enum: granularity
| Name | Value |
| ---- | ----- |
| granularity | day, week, month |



