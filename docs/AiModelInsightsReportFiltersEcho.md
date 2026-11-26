
# AiModelInsightsReportFiltersEcho

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **granularity** | [**inline**](#Granularity) |  |  |
| **competitors** | **kotlin.collections.List&lt;kotlin.Int&gt;** | Competitor ids from the competitors parameter; empty when it was not given |  |
| **countryCode** | **kotlin.String** | Comma-separated country codes |  [optional] |
| **languageCode** | **kotlin.String** | Comma-separated language codes |  [optional] |
| **collectionId** | **kotlin.String** | Comma-separated collection ids |  [optional] |
| **promptType** | **kotlin.String** | Comma-separated prompt types |  [optional] |
| **brandKind** | **kotlin.String** |  |  [optional] |
| **model** | [**inline**](#Model) | The model filter; always ai_overview on the AI Overview report |  [optional] |
| **brand1** | **kotlin.String** | Position distribution only. The id, as a string, of the competitor compared as the first brand; left out for the project brand |  [optional] |
| **brand2** | **kotlin.String** | Position distribution only. The id, as a string, of the competitor compared as the second brand, by default the competitor with the most mentions; left out when the project has none to compare |  [optional] |


<a id="Granularity"></a>
## Enum: granularity
| Name | Value |
| ---- | ----- |
| granularity | day, week, month |


<a id="Model"></a>
## Enum: model
| Name | Value |
| ---- | ----- |
| model | chatgpt, ai_mode, ai_overview, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode, bing_ai_overview |



