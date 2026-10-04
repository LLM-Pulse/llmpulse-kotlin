
# IntelligenceTaskUpdateResponse

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
| **resultData** | [**kotlin.Any**](.md) | The generated content once status is completed; null before that. A product_listing task returns title, summary, description_html (p, ul, ol, li, strong, em, h3 and br only), faq (question and answer pairs), seo_title, seo_description, image_alts (image_id and alt), changes (field and reason) and labels |  [optional] |
| **errorMessage** | **kotlin.String** |  |  [optional] |
| **estimatedTime** | **kotlin.String** |  |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **processedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **manuallyEditedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the content was last edited by hand; null while the output is as generated |  [optional] |
| **editedByUserId** | **kotlin.Int** | User behind the last manual edit; null for an unedited task or an edit made from an embedded portal |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |
| **changedPaths** | **kotlin.collections.List&lt;kotlin.String&gt;** | Paths whose text actually changed; empty when every value matched the stored text |  [optional] |



