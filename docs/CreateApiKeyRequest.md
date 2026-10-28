
# CreateApiKeyRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **name** | **kotlin.String** | A label to recognize the key, for example the customer it is for |  |
| **projectIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** | The projects the key is limited to, at least one |  |
| **scope** | [**inline**](#Scope) | read (default) only reads data; read_write can also create, change and delete within the key&#39;s projects |  [optional] |


<a id="Scope"></a>
## Enum: scope
| Name | Value |
| ---- | ----- |
| scope | read, read_write |



