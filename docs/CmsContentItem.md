
# CmsContentItem

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
| **excerpt** | **kotlin.String** | Plain-text excerpt, up to 2,000 characters |  [optional] |
| **contentHtml** | **kotlin.String** | Sanitized HTML (headings, paragraphs, lists, tables, quotes, code, links with href only), up to 200,000 characters |  [optional] |
| **contentTruncated** | **kotlin.Boolean** |  |  [optional] |


<a id="Type"></a>
## Enum: type
| Name | Value |
| ---- | ----- |
| type | post, page |



