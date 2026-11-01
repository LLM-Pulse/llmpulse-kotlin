
# ProjectDetailsAllOfPitchRun

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **status** | [**inline**](#Status) | starting before the run begins, running while answers arrive, ready once every AI model has answered or stopped trying |  [optional] |
| **launchedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **settledAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **models** | [**inline**](#kotlin.collections.List&lt;Models&gt;) | The AI models the run asks, fixed when it starts |  [optional] |
| **answersExpected** | **kotlin.Int** |  |  [optional] |
| **answersReceived** | **kotlin.Int** |  |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | starting, running, ready |


<a id="kotlin.collections.List<Models>"></a>
## Enum: models
| Name | Value |
| ---- | ----- |
| models | chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao |



