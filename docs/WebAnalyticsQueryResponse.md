
# WebAnalyticsQueryResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **provider** | [**inline**](#Provider) |  |  [optional] |
| **&#x60;property&#x60;** | **kotlin.String** |  |  [optional] |
| **columns** | [**kotlin.collections.List&lt;WebAnalyticsQueryResponseColumnsInner&gt;**](WebAnalyticsQueryResponseColumnsInner.md) |  |  [optional] |
| **rows** | **kotlin.collections.List&lt;kotlin.collections.List&lt;kotlin.Any&gt;&gt;** | One array per row, values in column order: strings, numbers or null. |  [optional] |
| **rowCount** | **kotlin.Int** | Rows in this response (at most 5,000). |  [optional] |
| **totalRows** | **kotlin.Int** | Rows the provider has for the query, when it reports it. |  [optional] |
| **truncated** | **kotlin.Boolean** | True when the provider has more rows than returned; page with its own offset or page field. |  [optional] |
| **totals** | [**kotlin.collections.Map&lt;kotlin.String, kotlin.Any&gt;**](kotlin.Any.md) | Metric totals by metric name, when the query asked for them. |  [optional] |
| **notes** | **kotlin.collections.List&lt;kotlin.String&gt;** | Provider caveats: sampling, thresholds, more rows available. |  [optional] |
| **meta** | [**kotlin.collections.Map&lt;kotlin.String, kotlin.Any&gt;**](kotlin.Any.md) | Provider metadata such as GA4 time zone, currency and remaining property quota. |  [optional] |
| **fetchedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the provider answered. |  [optional] |
| **cached** | **kotlin.Boolean** | True when the answer came from the 10-minute cache instead of the provider. |  [optional] |
| **query** | [**kotlin.collections.Map&lt;kotlin.String, kotlin.Any&gt;**](kotlin.Any.md) | The request as sent to the provider, with the connected property forced and limits applied. |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |


<a id="Provider"></a>
## Enum: provider
| Name | Value |
| ---- | ----- |
| provider | google_analytics, adobe_analytics, matomo, posthog, plausible, piano |



