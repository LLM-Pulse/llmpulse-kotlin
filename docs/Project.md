
# Project

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  [optional] |
| **name** | **kotlin.String** | Internal project label (sidebar, settings, admin) |  [optional] |
| **brandName** | **kotlin.String** | LLM-facing brand label (used in prompts and customer-facing charts). Null when not set, in which case prompts and charts use &#x60;name&#x60;. |  [optional] |
| **tracked** | **kotlin.Boolean** | Whether scheduled runs include this project. False when it is paused, or when the plan&#39;s project limit leaves it out (the oldest projects up to the limit run), so its prompts do not run |  [optional] |
| **untrackedReason** | **kotlin.String** | Why tracked is false: paused or project_limit. Null when tracked |  [optional] |



