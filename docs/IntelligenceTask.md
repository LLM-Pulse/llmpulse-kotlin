
# IntelligenceTask

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  [optional] |
| **publicId** | **kotlin.String** |  |  [optional] |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **taskType** | **kotlin.String** |  |  [optional] |
| **title** | **kotlin.String** |  |  [optional] |
| **status** | **kotlin.String** |  |  [optional] |
| **promptId** | **kotlin.Int** |  |  [optional] |
| **promptText** | **kotlin.String** |  |  [optional] |
| **agenticMode** | **kotlin.Boolean** |  |  [optional] |
| **customTopic** | **kotlin.String** |  |  [optional] |
| **userInstructions** | **kotlin.String** |  |  [optional] |
| **outputLanguageCode** | **kotlin.String** |  |  [optional] |
| **wordCount** | **kotlin.Int** |  |  [optional] |
| **resultData** | [**kotlin.Any**](.md) | Only present when status&#x3D;&#39;completed&#39; |  [optional] |
| **errorMessage** | **kotlin.String** |  |  [optional] |
| **estimatedTime** | **kotlin.String** |  |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **processedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **manuallyEditedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the content was last edited by hand; null while the output is as generated |  [optional] |
| **editedByUserId** | **kotlin.Int** | User behind the last manual edit; null for an unedited task or an edit made from an embedded portal |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



