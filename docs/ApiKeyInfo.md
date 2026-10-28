
# ApiKeyInfo

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **name** | **kotlin.String** |  |  |
| **prefix** | **kotlin.String** | The visible start of the token, to recognize the key. Never the secret itself. |  |
| **scope** | [**inline**](#Scope) |  |  |
| **projectScoped** | **kotlin.Boolean** | True when the key is limited to project_ids; false for an account-wide key. |  |
| **projectIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** | The projects the key is limited to; empty for an account-wide key. |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **lastUsedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | Updated at most once a minute. |  |
| **revokedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |


<a id="Scope"></a>
## Enum: scope
| Name | Value |
| ---- | ----- |
| scope | read, read_write |



