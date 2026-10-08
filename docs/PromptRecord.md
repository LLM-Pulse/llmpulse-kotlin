
# PromptRecord

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **promptText** | **kotlin.String** |  |  |
| **collectionId** | **kotlin.Int** | Primary tag, when the prompt has one |  |
| **collectionIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** | Every tag the prompt belongs to |  |
| **tags** | [**kotlin.collections.List&lt;TagRef&gt;**](TagRef.md) |  |  |
| **countryCode** | **kotlin.String** |  |  |
| **languageCode** | **kotlin.String** |  |  |
| **promptType** | **kotlin.String** | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified |  |
| **brandKind** | **kotlin.String** | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified |  |
| **lastExecutedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | Null until the prompt has run |  |
| **appUrl** | [**java.net.URI**](java.net.URI.md) | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project |  |



