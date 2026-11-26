
# CitationSeries

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **granularity** | [**inline**](#Granularity) |  |  |
| **total** | **kotlin.Int** | Equal to total_responses |  |
| **byModel** | **kotlin.collections.Map&lt;kotlin.String, kotlin.Int&gt;** | Answers per AI model, keyed by model, largest first |  |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;AiModelPositionDistributionBrandBucketsInnerDataInner&gt;**](AiModelPositionDistributionBrandBucketsInnerDataInner.md) | One point per period holding a filtered answer, oldest first; a zero means answers ran and none cited it |  |


<a id="Granularity"></a>
## Enum: granularity
| Name | Value |
| ---- | ----- |
| granularity | day, week, month |



