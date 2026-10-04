
# AiOrdersResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **platform** | **kotlin.String** |  |  |
| **currency** | **kotlin.String** | ISO 4217 code of the most recent stored day; null when the window holds no stored order |  |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  |
| **totals** | [**AiOrdersResponseTotals**](AiOrdersResponseTotals.md) |  |  |
| **bySource** | [**kotlin.collections.List&lt;AiOrdersResponseBySourceInner&gt;**](AiOrdersResponseBySourceInner.md) | One row per AI assistant, highest revenue first |  |
| **series** | [**kotlin.collections.List&lt;AiOrdersResponseSeriesInner&gt;**](AiOrdersResponseSeriesInner.md) | Days that have stored orders, oldest first |  |
| **requestId** | **kotlin.String** |  |  |



