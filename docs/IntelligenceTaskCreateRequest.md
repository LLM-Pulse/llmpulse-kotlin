
# IntelligenceTaskCreateRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **taskType** | [**inline**](#TaskType) | product_listing is API-only: it needs product and returns ready-to-apply product page copy |  |
| **promptId** | **kotlin.Int** | Not used by product_listing; send null or omit it |  [optional] |
| **customTopic** | **kotlin.String** |  |  [optional] |
| **userInstructions** | **kotlin.String** |  |  [optional] |
| **outputLanguageCode** | **kotlin.String** |  |  [optional] |
| **existingContent** | **kotlin.String** |  |  [optional] |
| **existingContentUrl** | [**java.net.URI**](java.net.URI.md) |  |  [optional] |
| **product** | [**IntelligenceTaskProduct**](IntelligenceTaskProduct.md) |  |  [optional] |
| **promptIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** | product_listing only: up to 20 project prompts the copy should answer |  [optional] |


<a id="TaskType"></a>
## Enum: task_type
| Name | Value |
| ---- | ----- |
| taskType | brief, create, update, pr_insights, custom, product_listing |



