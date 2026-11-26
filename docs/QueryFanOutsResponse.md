
# QueryFanOutsResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **page** | **kotlin.Int** |  |  |
| **perPage** | **kotlin.Int** |  |  |
| **total** | **kotlin.Int** | Rows matching the filters across every page |  |
| **requestId** | **kotlin.String** |  |  |
| **view** | **kotlin.String** | query or prompt, the row shape of data |  |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;QueryFanOutRow&gt;**](QueryFanOutRow.md) |  |  |
| **totalOccurrences** | **kotlin.Int** | Sub-query occurrences across every page (view&#x3D;query) |  [optional] |



