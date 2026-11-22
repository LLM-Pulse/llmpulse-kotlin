
# BingWebmasterListResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **site** | **kotlin.String** | The connected site, as Bing Webmaster Tools names it (e.g. https://example.com/) |  [optional] |
| **syncStatus** | **kotlin.String** | State of the daily sync: pending, syncing, completed, failed or on_hold (the data already synced still answers, but stops updating until the site is reconnected) |  [optional] |
| **lastSyncedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the site last synced. Null before its first sync, or while history_current is false. |  [optional] |
| **historyCurrent** | **kotlin.Boolean** | False right after the site was changed and before its first sync. Until then data is empty and data_through is null. |  [optional] |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **dataThrough** | [**java.time.LocalDate**](java.time.LocalDate.md) | The last week_ending synced for the site (the Friday that closes a Bing week) |  [optional] |
| **page** | **kotlin.Int** |  |  [optional] |
| **perPage** | **kotlin.Int** |  |  [optional] |
| **total** | **kotlin.Int** | Distinct pages or queries found in the weeks of the window |  [optional] |
| **sort** | **kotlin.String** |  |  [optional] |
| **weeksCovered** | **kotlin.Int** | Weeks with data whose week_ending falls in the window |  [optional] |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;BingWebmasterListResponseDataInner&gt;**](BingWebmasterListResponseDataInner.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



