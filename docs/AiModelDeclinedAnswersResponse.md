
# AiModelDeclinedAnswersResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | Start of the tracking period holding the first day asked for |  |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **model** | [**inline**](#Model) | The model the counts are for |  |
| **cadence** | **kotlin.String** | The account&#39;s current tracking cadence: daily, weekly or monthly. Chart periods before a switch from weekly to daily stay weekly. |  |
| **summary** | [**AiModelDeclinedAnswersResponseSummary**](AiModelDeclinedAnswersResponseSummary.md) |  |  |
| **chart** | [**kotlin.collections.List&lt;AiModelDeclinedAnswersResponseChartInner&gt;**](AiModelDeclinedAnswersResponseChartInner.md) | One point per tracking period holding an answer, oldest first. A period without answers has no point; a period with answers and no declines is a real 0. |  |
| **byPrompt** | [**AiModelDeclinedAnswersResponseByPrompt**](AiModelDeclinedAnswersResponseByPrompt.md) |  |  |
| **filters** | [**AiModelDeclinedAnswersResponseFilters**](AiModelDeclinedAnswersResponseFilters.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |


<a id="Model"></a>
## Enum: model
| Name | Value |
| ---- | ----- |
| model | gemini |



