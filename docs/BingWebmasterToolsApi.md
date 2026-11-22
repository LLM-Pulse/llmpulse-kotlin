# BingWebmasterToolsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getBingWebmasterPages**](BingWebmasterToolsApi.md#getBingWebmasterPages) | **GET** /bing_webmaster/pages | Top Bing Webmaster Tools pages (Growth+) |
| [**getBingWebmasterQueries**](BingWebmasterToolsApi.md#getBingWebmasterQueries) | **GET** /bing_webmaster/queries | Top Bing Webmaster Tools queries (Growth+) |
| [**getBingWebmasterSummary**](BingWebmasterToolsApi.md#getBingWebmasterSummary) | **GET** /bing_webmaster/summary | Bing Webmaster Tools summary (Growth+) |
| [**getBingWebmasterTimeseries**](BingWebmasterToolsApi.md#getBingWebmasterTimeseries) | **GET** /bing_webmaster/timeseries | Bing Webmaster Tools time series (Growth+) |


<a id="getBingWebmasterPages"></a>
# **getBingWebmasterPages**
> BingWebmasterListResponse getBingWebmasterPages(projectId, range, from, to, sort, page, perPage, output)

Top Bing Webmaster Tools pages (Growth+)

The landing pages of the project&#39;s connected Bing Webmaster Tools site in Bing Search, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top pages of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = BingWebmasterToolsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
val sort : kotlin.String = sort_example // kotlin.String | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last.
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : BingWebmasterListResponse = apiInstance.getBingWebmasterPages(projectId, range, from, to, sort, page, perPage, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling BingWebmasterToolsApi#getBingWebmasterPages")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling BingWebmasterToolsApi#getBingWebmasterPages")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **java.time.LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **java.time.LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **sort** | **kotlin.String**| Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional] [default to Sort.impressions] [enum: impressions, clicks, ctr, avg_impression_position, avg_click_position] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**BingWebmasterListResponse**](BingWebmasterListResponse.md)

### Authorization


Configure BearerAuth statically:
```kotlin
ApiClient.accessToken = ""
```
Configure BearerAuth dynamically:
```kotlin
apiInstance.accessTokenProvider = { "" }
```

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getBingWebmasterQueries"></a>
# **getBingWebmasterQueries**
> BingWebmasterListResponse getBingWebmasterQueries(projectId, range, from, to, sort, page, perPage, output)

Top Bing Webmaster Tools queries (Growth+)

The Bing search queries of the project&#39;s connected Bing Webmaster Tools site, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top queries of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = BingWebmasterToolsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
val sort : kotlin.String = sort_example // kotlin.String | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last.
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : BingWebmasterListResponse = apiInstance.getBingWebmasterQueries(projectId, range, from, to, sort, page, perPage, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling BingWebmasterToolsApi#getBingWebmasterQueries")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling BingWebmasterToolsApi#getBingWebmasterQueries")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **java.time.LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **java.time.LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **sort** | **kotlin.String**| Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional] [default to Sort.impressions] [enum: impressions, clicks, ctr, avg_impression_position, avg_click_position] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**BingWebmasterListResponse**](BingWebmasterListResponse.md)

### Authorization


Configure BearerAuth statically:
```kotlin
ApiClient.accessToken = ""
```
Configure BearerAuth dynamically:
```kotlin
apiInstance.accessTokenProvider = { "" }
```

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getBingWebmasterSummary"></a>
# **getBingWebmasterSummary**
> BingWebmasterSummaryResponse getBingWebmasterSummary(projectId, range, from, to)

Bing Webmaster Tools summary (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project&#39;s connected Bing Webmaster Tools site over a date range, summed from the daily site totals synced once a day. Bing reports no average position in its daily totals. About 13 months of history are kept; data_through is the last day synced, and later days are missing, not zero. history_current is false right after the site was changed in Preferences &gt; Project Settings &gt; Connections and before its first sync: the totals are then zero and data_through and last_synced_at null. A connection whose sync_status is on_hold (Bing refused the stored API key, or the site is no longer verified) still answers from the data already synced. Requires a connected Bing Webmaster Tools site and the Growth plan or above; otherwise returns ERR_BING_WEBMASTER_NOT_CONNECTED (with meta.connect_url) or ERR_PLAN_REQUIRED.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = BingWebmasterToolsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
try {
    val result : BingWebmasterSummaryResponse = apiInstance.getBingWebmasterSummary(projectId, range, from, to)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling BingWebmasterToolsApi#getBingWebmasterSummary")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling BingWebmasterToolsApi#getBingWebmasterSummary")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **java.time.LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **to** | **java.time.LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |

### Return type

[**BingWebmasterSummaryResponse**](BingWebmasterSummaryResponse.md)

### Authorization


Configure BearerAuth statically:
```kotlin
ApiClient.accessToken = ""
```
Configure BearerAuth dynamically:
```kotlin
apiInstance.accessTokenProvider = { "" }
```

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getBingWebmasterTimeseries"></a>
# **getBingWebmasterTimeseries**
> BingWebmasterTimeseriesResponse getBingWebmasterTimeseries(projectId, range, from, to, granularity, output)

Bing Webmaster Tools time series (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project&#39;s connected Bing Webmaster Tools site, bucketed by day, week (starting Monday) or month from the daily site totals synced once a day. Days without synced data are left out of the series, not reported as zero. Bing reports no average position in its daily totals. About 13 months of history are kept. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = BingWebmasterToolsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
val granularity : kotlin.String = granularity_example // kotlin.String | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : BingWebmasterTimeseriesResponse = apiInstance.getBingWebmasterTimeseries(projectId, range, from, to, granularity, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling BingWebmasterToolsApi#getBingWebmasterTimeseries")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling BingWebmasterToolsApi#getBingWebmasterTimeseries")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **java.time.LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **java.time.LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**BingWebmasterTimeseriesResponse**](BingWebmasterTimeseriesResponse.md)

### Authorization


Configure BearerAuth statically:
```kotlin
ApiClient.accessToken = ""
```
Configure BearerAuth dynamically:
```kotlin
apiInstance.accessTokenProvider = { "" }
```

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

