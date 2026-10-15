
# PromptGenerationResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | [**java.util.UUID**](java.util.UUID.md) | The run id; poll GET /prompt_generations/{id} with it (kept for 24 hours) |  |
| **projectId** | **kotlin.Int** |  |  |
| **source** | **kotlin.String** |  |  |
| **status** | [**inline**](#Status) |  |  |
| **params** | [**PromptGenerationResponseParams**](PromptGenerationResponseParams.md) |  |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **finishedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **suggestionsCount** | **kotlin.Int** |  |  |
| **suggestions** | [**kotlin.collections.List&lt;SuggestedPrompt&gt;**](SuggestedPrompt.md) | The suggestions the run saved to the Suggested prompts queue, with their current status |  |
| **error** | [**PromptGenerationResponseError**](PromptGenerationResponseError.md) |  |  |
| **requestId** | **kotlin.String** |  |  |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | processing, completed, failed |



