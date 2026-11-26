
# AnswerRecord

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **promptId** | **kotlin.Int** |  |  |
| **promptText** | **kotlin.String** |  |  |
| **model** | [**inline**](#Model) |  |  |
| **executedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **durationMs** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Milliseconds our pipeline spent processing the collected answer, rounded to one decimal place |  |
| **noResult** | **kotlin.Boolean** | True for a sentinel non-answer (no answer could be collected after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics |  |
| **mentionsCount** | **kotlin.Int** | Mentions of your brand in the answer |  |
| **citationsCount** | **kotlin.Int** | Citations of your brand in the answer |  |
| **appUrl** | [**java.net.URI**](java.net.URI.md) | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |  |
| **noResultReason** | [**inline**](#NoResultReason) | Present only when no_result is true. declined &#x3D; the model declined to answer and response holds its reply; no_answer &#x3D; no answer could be collected |  [optional] |
| **response** | **kotlin.String** | The answer text, cut to 10,000 characters (without query) |  [optional] |
| **responseTruncated** | **kotlin.Boolean** | Whether response was cut (without query) |  [optional] |
| **snippet** | **kotlin.String** | The text around the first match (with query) |  [optional] |
| **matchCount** | **kotlin.Int** | Matches of query in the answer (with query) |  [optional] |


<a id="Model"></a>
## Enum: model
| Name | Value |
| ---- | ----- |
| model | chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode, bing_ai_overview |


<a id="NoResultReason"></a>
## Enum: no_result_reason
| Name | Value |
| ---- | ----- |
| noResultReason | declined, no_answer |



