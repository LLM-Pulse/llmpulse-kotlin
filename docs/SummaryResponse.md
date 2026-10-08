
# SummaryResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **granularity** | **kotlin.String** | day, week or month |  [optional] |
| **filters** | [**MetricsFiltersEcho**](MetricsFiltersEcho.md) |  |  [optional] |
| **series** | **kotlin.collections.Map&lt;kotlin.String, kotlin.collections.List&lt;TimeseriesSeries&gt;&gt;** |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |
| **summary** | **kotlin.collections.Map&lt;kotlin.String, kotlin.collections.List&lt;SummaryResponseAllOfSummaryValueInner&gt;&gt;** |  |  [optional] |
| **positionDistribution** | [**SummaryResponseAllOfPositionDistribution**](SummaryResponseAllOfPositionDistribution.md) |  |  [optional] |



