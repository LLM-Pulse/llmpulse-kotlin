
# AdRow

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **domain** | **kotlin.String** | Advertising domain; null on a placement that names none (view&#x3D;ads) |  |
| **ads** | **kotlin.Int** | Placements of the domain (view&#x3D;advertisers) |  [optional] |
| **executions** | **kotlin.Int** | Answers that carried them (view&#x3D;advertisers) |  [optional] |
| **prompts** | **kotlin.Int** | Distinct prompts that triggered them (view&#x3D;advertisers) |  [optional] |
| **avgPosition** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Average position, 1 is the best slot; null when no placement has one (view&#x3D;advertisers) |  [optional] |
| **bestPosition** | **kotlin.Int** | Best position, 1 is the best slot (view&#x3D;advertisers) |  [optional] |
| **id** | **kotlin.Int** | The placement (view&#x3D;ads) |  [optional] |
| **model** | [**inline**](#Model) |  |  [optional] |
| **title** | **kotlin.String** |  |  [optional] |
| **snippet** | **kotlin.String** |  |  [optional] |
| **url** | **kotlin.String** |  |  [optional] |
| **position** | **kotlin.Int** | Position of the placement, 1 is the best slot (view&#x3D;ads) |  [optional] |
| **isClient** | **kotlin.Boolean** | Whether the placement is identified as your brand&#39;s own (view&#x3D;ads) |  [optional] |
| **promptId** | **kotlin.Int** |  |  [optional] |
| **promptText** | **kotlin.String** |  |  [optional] |
| **promptExecutionId** | **kotlin.Int** |  |  [optional] |
| **executedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the answer that carried the placement was collected (view&#x3D;ads) |  [optional] |


<a id="Model"></a>
## Enum: model
| Name | Value |
| ---- | ----- |
| model | chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode, bing_ai_overview |



