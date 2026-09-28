
# Competitor

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  [optional] |
| **name** | **kotlin.String** |  |  [optional] |
| **domain** | **kotlin.String** | Bare (scheme-less) domain. Null only on the own-brand row (include_project_brand&#x3D;true) when the project has no URL. |  [optional] |
| **actorType** | [**inline**](#ActorType) | Only present when include_project_brand&#x3D;true |  [optional] |
| **isOwn** | **kotlin.Boolean** | Only present when include_project_brand&#x3D;true |  [optional] |


<a id="ActorType"></a>
## Enum: actor_type
| Name | Value |
| ---- | ----- |
| actorType | project, competitor |



