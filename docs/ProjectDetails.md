
# ProjectDetails

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  [optional] |
| **name** | **kotlin.String** | Internal project label (sidebar, settings, admin) |  [optional] |
| **brandName** | **kotlin.String** | LLM-facing brand label (used in prompts and customer-facing charts). Defaults to &#x60;name&#x60; when not set. |  [optional] |
| **url** | [**java.net.URI**](java.net.URI.md) |  |  [optional] |
| **description** | **kotlin.String** |  |  [optional] |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **industry** | **kotlin.String** |  |  [optional] |
| **businessModel** | **kotlin.String** |  |  [optional] |
| **businessModelOther** | **kotlin.String** | Set only when business_model is OTHER |  [optional] |
| **primaryProducts** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **targetAudience** | **kotlin.String** |  |  [optional] |
| **brandVoice** | **kotlin.String** |  |  [optional] |
| **goals** | **kotlin.String** |  |  [optional] |
| **countryCode** | **kotlin.String** |  |  [optional] |
| **languageCode** | **kotlin.String** |  |  [optional] |
| **paused** | **kotlin.Boolean** |  |  [optional] |
| **googlePlayId** | **kotlin.String** |  |  [optional] |
| **appStoreId** | **kotlin.String** |  |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **stats** | [**ProjectDetailsAllOfStats**](ProjectDetailsAllOfStats.md) |  |  [optional] |



