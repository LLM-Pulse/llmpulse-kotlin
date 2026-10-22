
# SearchConsolePropertiesResponseDataInner

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.String** | Property id, the value the property parameter takes, e.g. sc-domain:example.com |  [optional] |
| **name** | **kotlin.String** |  |  [optional] |
| **primary** | **kotlin.Boolean** | The property read when the property parameter is omitted |  [optional] |
| **type** | [**inline**](#Type) |  |  [optional] |
| **status** | [**inline**](#Status) |  |  [optional] |
| **lastSyncedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |


<a id="Type"></a>
## Enum: type
| Name | Value |
| ---- | ----- |
| type | domain, url_prefix |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | connected, reconnect_required |



