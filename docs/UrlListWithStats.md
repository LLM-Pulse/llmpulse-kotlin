
# UrlListWithStats

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **name** | **kotlin.String** |  |  |
| **description** | **kotlin.String** |  |  |
| **currency** | [**inline**](#Currency) | The currency of the entry costs. |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **updatedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **entriesCount** | **kotlin.Int** |  |  |
| **citedEntries** | **kotlin.Int** | Entries an AI answer cited in the window. |  |
| **citations** | **kotlin.Int** | AI answers citing any entry in the window, each once. |  |
| **lastCitedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | The latest answer citing an entry, up to the window&#39;s end. |  |


<a id="Currency"></a>
## Enum: currency
| Name | Value |
| ---- | ----- |
| currency | USD, EUR, GBP |



