
# RedditResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **page** | **kotlin.Int** |  |  |
| **perPage** | **kotlin.Int** |  |  |
| **total** | **kotlin.Int** | Rows matching the filters across every page |  |
| **requestId** | **kotlin.String** |  |  |
| **view** | **kotlin.String** | subreddits, authors, threads or breakdowns |  |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | Start of the window, 30 days back by default |  |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;RedditRow&gt;**](RedditRow.md) |  |  |
| **citations** | **kotlin.Int** | Reddit citations after the filters (view&#x3D;breakdowns) |  [optional] |



