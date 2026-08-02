
# SummaryResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **granularity** | **kotlin.String** |  |  [optional] |
| **filters** | [**kotlin.Any**](.md) |  |  [optional] |
| **series** | **kotlin.collections.Map&lt;kotlin.String, kotlin.collections.List&lt;TimeseriesSeries&gt;&gt;** |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |
| **summary** | **kotlin.collections.Map&lt;kotlin.String, kotlin.collections.List&lt;SummaryResponseAllOfSummaryValueInner&gt;&gt;** |  |  [optional] |
| **positionDistribution** | [**SummaryResponseAllOfPositionDistribution**](SummaryResponseAllOfPositionDistribution.md) |  |  [optional] |



