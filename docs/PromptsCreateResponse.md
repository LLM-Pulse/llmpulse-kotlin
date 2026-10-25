
# PromptsCreateResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **created** | **kotlin.Int** |  |  [optional] |
| **skipped** | **kotlin.Int** |  |  [optional] |
| **totalAfter** | **kotlin.Int** |  |  [optional] |
| **promptsAvailable** | **kotlin.Int** |  |  [optional] |
| **tracked** | **kotlin.Boolean** | Whether scheduled runs include the project the prompts were added to. False when it is paused or beyond the plan&#39;s project limit, so the new prompts do not run until that changes |  [optional] |
| **untrackedReason** | **kotlin.String** | Why tracked is false: paused or project_limit. Null when tracked |  [optional] |
| **warning** | **kotlin.String** | What to do when tracked is false. Null when tracked |  [optional] |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;PromptsCreateResponseDataInner&gt;**](PromptsCreateResponseDataInner.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



