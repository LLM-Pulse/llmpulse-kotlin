
# SovResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **periods** | [**kotlin.collections.List&lt;SovResponsePeriodsInner&gt;**](SovResponsePeriodsInner.md) | Per-bucket sample size and completeness: mentions is the total the shares were computed on (1-3 mentions produce the 100/50/33.33 low-sample patterns); partial marks buckets still collecting data or clipped by the requested window. |  [optional] |
| **overTime** | [**kotlin.collections.List&lt;SovResponseOverTimeInner&gt;**](SovResponseOverTimeInner.md) |  |  [optional] |
| **current** | [**kotlin.collections.List&lt;SovResponseCurrentInner&gt;**](SovResponseCurrentInner.md) |  |  [optional] |
| **breakdown** | [**kotlin.collections.List&lt;SovResponseBreakdownInner&gt;**](SovResponseBreakdownInner.md) |  |  [optional] |
| **others** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) |  |  [optional] |



