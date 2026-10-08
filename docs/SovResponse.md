
# SovResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **granularity** | **kotlin.String** | day, week or month |  [optional] |
| **filters** | [**MetricsFiltersEcho**](MetricsFiltersEcho.md) |  |  [optional] |
| **periods** | [**kotlin.collections.List&lt;SovResponsePeriodsInner&gt;**](SovResponsePeriodsInner.md) | Per-bucket sample size and completeness: mentions is the total the shares were computed on (1-3 mentions produce the 100/50/33.33 low-sample patterns); partial marks buckets still collecting data or clipped by the requested window; confidence and margin_of_error read the sample size. |  [optional] |
| **sample** | [**SovResponseSample**](SovResponseSample.md) |  |  [optional] |
| **overTime** | [**kotlin.collections.List&lt;SovResponseOverTimeInner&gt;**](SovResponseOverTimeInner.md) |  |  [optional] |
| **current** | [**kotlin.collections.List&lt;SovResponseCurrentInner&gt;**](SovResponseCurrentInner.md) |  |  [optional] |
| **breakdown** | [**kotlin.collections.List&lt;SovResponseBreakdownInner&gt;**](SovResponseBreakdownInner.md) |  |  [optional] |
| **others** | [**kotlin.collections.List&lt;SovResponseOthersInner&gt;**](SovResponseOthersInner.md) | Actors ranked fifth and below, folded into the Others share of breakdown |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



