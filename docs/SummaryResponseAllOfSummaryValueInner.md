
# SummaryResponseAllOfSummaryValueInner

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **actor** | [**Actor**](Actor.md) |  |  [optional] |
| **metric** | **kotlin.String** |  |  [optional] |
| **total** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Count metrics sum the buckets; rate, position and sentiment metrics average them. ai_visibility_score (weighted_visibility) is the window&#39;s points divided by its data days (the days with responses under the filters), the number the app shows, whatever the granularity. |  [optional] |
| **aggregation** | [**inline**](#Aggregation) | How total combines the buckets (average for ai_visibility_score, a per-data-day score) |  [optional] |
| **min** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **max** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **last** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |


<a id="Aggregation"></a>
## Enum: aggregation
| Name | Value |
| ---- | ----- |
| aggregation | sum, average |



