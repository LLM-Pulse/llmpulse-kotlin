
# CatalogPromptSuggestion

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **prompt** | **kotlin.String** |  |  |
| **status** | **kotlin.String** | pending, accepted or rejected |  |
| **source** | **kotlin.String** | Always catalog |  |
| **countryCode** | **kotlin.String** |  |  |
| **languageCode** | **kotlin.String** |  |  |
| **product** | [**CatalogPromptSuggestionProduct**](CatalogPromptSuggestionProduct.md) |  |  |
| **promptId** | **kotlin.Int** | The tracked prompt an accepted suggestion became; null until accepted |  |
| **acceptedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the suggestion was accepted; null until then |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |



