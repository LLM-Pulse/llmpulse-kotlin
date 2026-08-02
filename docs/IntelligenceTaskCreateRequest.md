
# IntelligenceTaskCreateRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **taskType** | [**inline**](#TaskType) |  |  |
| **promptId** | **kotlin.Int** |  |  [optional] |
| **customTopic** | **kotlin.String** |  |  [optional] |
| **userInstructions** | **kotlin.String** |  |  [optional] |
| **outputLanguageCode** | **kotlin.String** |  |  [optional] |
| **existingContent** | **kotlin.String** |  |  [optional] |
| **existingContentUrl** | [**java.net.URI**](java.net.URI.md) |  |  [optional] |


<a id="TaskType"></a>
## Enum: task_type
| Name | Value |
| ---- | ----- |
| taskType | brief, create, update, pr_insights, custom |



