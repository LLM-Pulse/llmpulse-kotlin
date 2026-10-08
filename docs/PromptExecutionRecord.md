
# PromptExecutionRecord

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **promptId** | **kotlin.Int** |  |  |
| **executedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | Null while the answer is still pending |  |
| **durationMs** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  |
| **success** | **kotlin.Boolean** | Null while the answer is still pending |  |
| **model** | [**inline**](#Model) |  |  |
| **fanOutQueries** | **kotlin.collections.List&lt;kotlin.String&gt;** | Sub-queries the model issued while answering; null when the model reports none |  |
| **hasMention** | **kotlin.Boolean** |  |  |
| **hasCitation** | **kotlin.Boolean** |  |  |
| **mentionsCount** | **kotlin.Int** | 1 when the answer mentions the brand, otherwise 0 |  |
| **citationsCount** | **kotlin.Int** | 1 when the answer cites the brand, otherwise 0 |  |
| **appUrl** | [**java.net.URI**](java.net.URI.md) | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |  |


<a id="Model"></a>
## Enum: model
| Name | Value |
| ---- | ----- |
| model | chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai |



