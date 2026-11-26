
# CitedUrlOccurrencesResponseAllOfData

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **sourceId** | **kotlin.Int** |  |  |
| **answerId** | **kotlin.Int** |  |  |
| **promptExecutionId** | **kotlin.Int** | Same as answer_id |  |
| **promptId** | **kotlin.Int** |  |  |
| **promptText** | **kotlin.String** |  |  |
| **model** | [**inline**](#Model) |  |  |
| **executedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **citationPosition** | **kotlin.Int** | Rank of the citation in the answer; 0 for a background source reference |  |
| **url** | **kotlin.String** | Normalized cited URL |  |
| **domain** | **kotlin.String** |  |  |
| **sourceType** | **kotlin.String** | owned, competitor or third_party |  |
| **responseExcerpt** | **kotlin.String** | The first 600 characters of the answer |  |
| **responseTruncated** | **kotlin.Boolean** |  |  |
| **fanOutQueries** | **kotlin.collections.List&lt;kotlin.String&gt;** | Sub-queries the model issued while answering; null when the model reports none |  |


<a id="Model"></a>
## Enum: model
| Name | Value |
| ---- | ----- |
| model | chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode, bing_ai_overview |



