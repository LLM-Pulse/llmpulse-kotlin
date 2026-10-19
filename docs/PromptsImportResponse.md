
# PromptsImportResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **processedRows** | **kotlin.Int** | Distinct rows imported or matched to an existing prompt |  |
| **created** | **kotlin.Int** |  |  |
| **duplicates** | **kotlin.Int** | Rows that matched an existing prompt (they still get the row&#39;s tags, unless a team member lacks update access to Prompts) |  |
| **tagged** | **kotlin.Int** | New prompt-tag links |  |
| **createdTags** | **kotlin.Int** |  |  |
| **rowErrors** | [**kotlin.collections.List&lt;PromptsImportResponseRowErrorsInner&gt;**](PromptsImportResponseRowErrorsInner.md) | Rows that were skipped or whose tags were not added, by their index in rows |  |
| **lengthWarning** | **kotlin.String** | Which tracked AI models will skip new prompts that are too long for them |  |
| **promptsAvailable** | **kotlin.Int** | Prompt slots left on the plan; null when unlimited |  |
| **requestId** | **kotlin.String** |  |  |



