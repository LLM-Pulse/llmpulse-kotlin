
# UpdateRecommendationItemRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **status** | [**inline**](#Status) | completed, archived, or active to restore the item |  |
| **reason** | [**inline**](#Reason) | Optional, with status archived only. competitor only on a PR &amp; Citation Building item that targets a domain. |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | active, completed, archived |


<a id="Reason"></a>
## Enum: reason
| Name | Value |
| ---- | ----- |
| reason | not_relevant, too_complex, competitor |



