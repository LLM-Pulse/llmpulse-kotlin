
# AiTrafficResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **provider** | **kotlin.String** | The connected provider: google_analytics, adobe_analytics, adobe_cja, posthog, plausible, matomo or piano |  |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  |
| **granularity** | [**inline**](#Granularity) |  |  |
| **totals** | [**AiTrafficResponseTotals**](AiTrafficResponseTotals.md) |  |  |
| **bySource** | [**kotlin.collections.List&lt;AiTrafficResponseBySourceInner&gt;**](AiTrafficResponseBySourceInner.md) | One row per AI source with traffic in the window, most sessions first |  |
| **timeseries** | **kotlin.collections.Map&lt;kotlin.String, kotlin.collections.Map&lt;kotlin.String, kotlin.Int&gt;&gt;** | Sessions keyed by AI source slug, then by the first day of the period (YYYY-MM-DD); a period without traffic is left out |  |
| **requestId** | **kotlin.String** |  |  |


<a id="Granularity"></a>
## Enum: granularity
| Name | Value |
| ---- | ----- |
| granularity | day, week, month |



