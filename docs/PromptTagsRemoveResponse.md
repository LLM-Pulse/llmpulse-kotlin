
# PromptTagsRemoveResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **promptsTargeted** | **kotlin.Int** | Prompts of the project among prompt_ids |  |
| **tagsDetached** | [**kotlin.collections.List&lt;TagRef&gt;**](TagRef.md) |  |  |
| **linksRemoved** | **kotlin.Int** |  |  |
| **skippedNotLinked** | **kotlin.Int** |  |  |
| **missingTagNames** | **kotlin.collections.List&lt;kotlin.String&gt;** | tag_names that matched no tag |  |
| **ignoredPromptIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** | prompt_ids that are not prompts of this project |  |
| **requestId** | **kotlin.String** |  |  |



