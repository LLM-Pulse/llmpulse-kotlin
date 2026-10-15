
# OwnedMediaCitingPromptsResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **provider** | **kotlin.String** |  |  [optional] |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **item** | [**OwnedMediaCitedItem**](OwnedMediaCitedItem.md) |  |  [optional] |
| **citationCount** | **kotlin.Int** | Citations of the item in the window |  [optional] |
| **promptCount** | **kotlin.Int** | Distinct prompts whose answers cited it |  [optional] |
| **page** | **kotlin.Int** |  |  [optional] |
| **perPage** | **kotlin.Int** |  |  [optional] |
| **total** | **kotlin.Int** | Citing answers |  [optional] |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;OwnedMediaCitingAnswer&gt;**](OwnedMediaCitingAnswer.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



