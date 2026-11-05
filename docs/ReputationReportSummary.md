
# ReputationReportSummary

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.String** | Report id for GET /reputation/reports/{id} |  |
| **status** | [**inline**](#Status) |  |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **availableModels** | [**inline**](#kotlin.collections.List&lt;AvailableModels&gt;) | Analyst models that produced data |  |
| **missingModels** | [**inline**](#kotlin.collections.List&lt;MissingModels&gt;) | Analyst models with no data yet |  |
| **processedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **errorMessage** | **kotlin.String** | Why the report failed; null unless status is failed |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | pending, processing, completed, failed |


<a id="kotlin.collections.List<AvailableModels>"></a>
## Enum: available_models
| Name | Value |
| ---- | ----- |
| availableModels | chatgpt, perplexity, gemini, deepseek, grok, claude |


<a id="kotlin.collections.List<MissingModels>"></a>
## Enum: missing_models
| Name | Value |
| ---- | ----- |
| missingModels | chatgpt, perplexity, gemini, deepseek, grok, claude |



