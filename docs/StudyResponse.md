
# StudyResponse

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
| **brief** | **kotlin.String** | What the study asks the analyst models; null when none was written |  |
| **subjects** | **kotlin.collections.List&lt;kotlin.String&gt;** | Names of the subjects it compares |  |
| **dimensions** | **kotlin.collections.List&lt;kotlin.String&gt;** | Keys of the dimensions it scores, as the dimension filter takes them |  |
| **reports** | [**kotlin.collections.List&lt;ReputationReportSummary&gt;**](ReputationReportSummary.md) | The 24 latest reports, newest first |  |
| **requestId** | **kotlin.String** |  |  |


<a id="kotlin.collections.List<AiModels>"></a>
## Enum: ai_models
| Name | Value |
| ---- | ----- |
| aiModels | chatgpt, perplexity, gemini, deepseek, grok, claude |



