
# RecommendationItem

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **recommendationId** | **kotlin.Int** |  |  |
| **recommendationType** | **kotlin.String** |  |  |
| **category** | **kotlin.String** |  |  |
| **title** | **kotlin.String** |  |  |
| **priority** | [**inline**](#Priority) |  |  |
| **actionItems** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  |
| **sourceRefs** | **kotlin.collections.List&lt;kotlin.String&gt;** | Evidence codes (e.g. P1, C2) resolved in resolved_source_refs |  |
| **status** | [**inline**](#Status) |  |  |
| **position** | **kotlin.Int** |  |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **updatedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **description** | **kotlin.String** |  |  [optional] |
| **estimatedImpact** | **kotlin.String** |  |  [optional] |
| **statusChangedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **metadata** | [**kotlin.collections.Map&lt;kotlin.String, kotlin.Any&gt;**](kotlin.Any.md) | Free-form details. Carries effort (low, medium or high) when the generator rated it, archive_reason (not_relevant, too_complex or competitor) on an item archived with a reason, and domain on PR &amp; Citation Building items. |  [optional] |
| **resolvedSourceRefs** | **kotlin.collections.List&lt;kotlin.collections.Map&lt;kotlin.String, kotlin.Any&gt;&gt;** | The evidence each source_refs code points to (prompt, citation or own page) |  [optional] |
| **unresolvedSourceRefs** | **kotlin.collections.List&lt;kotlin.String&gt;** | Present only when a code points to no stored evidence |  [optional] |


<a id="Priority"></a>
## Enum: priority
| Name | Value |
| ---- | ----- |
| priority | high, medium, low |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | active, completed, archived |



