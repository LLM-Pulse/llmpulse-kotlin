
# CmsContentSummary

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** | WordPress post or page id |  [optional] |
| **type** | [**inline**](#Type) |  |  [optional] |
| **status** | **kotlin.String** | WordPress status (publish, future, draft, pending or private) |  [optional] |
| **slug** | **kotlin.String** |  |  [optional] |
| **title** | **kotlin.String** | Plain-text title as the site renders it |  [optional] |
| **url** | **kotlin.String** | The public link on the connected site; null when the site names a link on another host |  [optional] |
| **modifiedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |


<a id="Type"></a>
## Enum: type
| Name | Value |
| ---- | ----- |
| type | post, page |



