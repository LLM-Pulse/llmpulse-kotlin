
# AgentTrafficResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **groupBy** | [**inline**](#GroupBy) |  |  [optional] |
| **granularity** | [**inline**](#Granularity) |  |  [optional] |
| **totals** | **kotlin.collections.Map&lt;kotlin.String, kotlin.Int&gt;** |  |  [optional] |
| **timeseries** | **kotlin.collections.Map&lt;kotlin.String, kotlin.collections.Map&lt;kotlin.String, kotlin.Int&gt;&gt;** |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |


<a id="GroupBy"></a>
## Enum: group_by
| Name | Value |
| ---- | ----- |
| groupBy | bot, company |


<a id="Granularity"></a>
## Enum: granularity
| Name | Value |
| ---- | ----- |
| granularity | day, week, month |



