
# SentimentRecord

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **promptExecutionId** | **kotlin.Int** |  |  |
| **promptText** | **kotlin.String** |  |  |
| **model** | [**inline**](#Model) |  |  |
| **analysis** | [**inline**](#Analysis) |  |  |
| **score** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | From -1 (very negative) to 1 (very positive) |  |
| **comment** | **kotlin.String** |  |  |
| **topics** | **kotlin.String** | Comma-separated topics |  |
| **competitorId** | **kotlin.Int** | Null for a sentiment about the project&#39;s own brand |  |
| **competitorName** | **kotlin.String** | Null for a sentiment about the project&#39;s own brand |  |
| **isBrandSentiment** | **kotlin.Boolean** |  |  |
| **executedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |


<a id="Model"></a>
## Enum: model
| Name | Value |
| ---- | ----- |
| model | chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai |


<a id="Analysis"></a>
## Enum: analysis
| Name | Value |
| ---- | ----- |
| analysis | very_positive, positive, neutral, negative, very_negative |



