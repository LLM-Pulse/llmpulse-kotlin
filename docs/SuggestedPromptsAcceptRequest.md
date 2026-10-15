
# SuggestedPromptsAcceptRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **ids** | **kotlin.collections.List&lt;kotlin.Int&gt;** | Suggestion ids to accept (max 100) |  |
| **tagIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** | One tag id to put the new prompts in |  [optional] |
| **tagNames** | **kotlin.collections.List&lt;kotlin.String&gt;** | One tag name (case-insensitive) to put the new prompts in |  [optional] |
| **createMissing** | **kotlin.Boolean** | Create the tag named in tag_names when it does not exist |  [optional] |



