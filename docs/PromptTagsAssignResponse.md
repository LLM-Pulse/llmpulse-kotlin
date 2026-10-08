
# PromptTagsAssignResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **promptsTargeted** | **kotlin.Int** | Prompts of the project among prompt_ids |  |
| **tagsAttached** | [**kotlin.collections.List&lt;TagRef&gt;**](TagRef.md) |  |  |
| **newLinksCreated** | **kotlin.Int** |  |  |
| **skippedAlreadyLinked** | **kotlin.Int** |  |  |
| **missingTagNames** | **kotlin.collections.List&lt;kotlin.String&gt;** | tag_names that matched no tag and were not created |  |
| **ignoredPromptIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** | prompt_ids that are not prompts of this project |  |
| **requestId** | **kotlin.String** |  |  |



