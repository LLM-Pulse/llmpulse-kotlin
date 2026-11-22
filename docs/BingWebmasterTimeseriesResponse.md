
# BingWebmasterTimeseriesResponse

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
| **dataThrough** | [**java.time.LocalDate**](java.time.LocalDate.md) | The last day synced for the site. Later days are missing, not zero. |  [optional] |
| **granularity** | **kotlin.String** |  |  [optional] |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;BingWebmasterTimeseriesResponseDataInner&gt;**](BingWebmasterTimeseriesResponseDataInner.md) | One bucket per day, week (starting Monday) or month that has synced days. Days without data are left out, not reported as zero. |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



