
# StudySummary

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **title** | **kotlin.String** |  |  |
| **studyType** | **kotlin.String** | brand_set, sector, geo, topic or custom |  |
| **cadence** | **kotlin.String** | one_shot or monthly |  |
| **status** | **kotlin.String** | active or archived |  |
| **projectId** | **kotlin.Int** | The project the study is attached to; null for an account-level study |  |
| **subjectsCount** | **kotlin.Int** |  |  |
| **aiModels** | [**inline**](#kotlin.collections.List&lt;AiModels&gt;) | Analyst models the study runs on |  |
| **outputLanguageCode** | **kotlin.String** | ISO 639-1 code of the language the reports are written in |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **lastReportAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the latest report started; null before the first one |  |


<a id="kotlin.collections.List<AiModels>"></a>
## Enum: ai_models
| Name | Value |
| ---- | ----- |
| aiModels | chatgpt, perplexity, gemini, deepseek, grok, claude |



