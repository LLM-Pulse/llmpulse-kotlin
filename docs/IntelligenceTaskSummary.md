
# IntelligenceTaskSummary

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **publicId** | **kotlin.String** |  |  |
| **taskType** | **kotlin.String** |  |  |
| **title** | **kotlin.String** |  |  |
| **status** | **kotlin.String** |  |  |
| **promptId** | **kotlin.Int** |  |  |
| **promptText** | **kotlin.String** |  |  |
| **wordCount** | **kotlin.Int** |  |  |
| **manuallyEditedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the content was last edited by hand; null while the output is as generated |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **processedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **resultVersion** | **kotlin.String** | Concurrency token for content edits: send it back as result_version on PATCH /intelligence_tasks/{id} so an edit composed before a regeneration is refused with ERR_STALE_CONTENT (409). It is \&quot;0\&quot; until the task first completes, then changes each time a generation or regeneration replaces result_data, never on a manual edit or a revert. Treat it as opaque text |  |



