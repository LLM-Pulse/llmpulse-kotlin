# SearchConsoleApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getSearchConsolePages**](SearchConsoleApi.md#getSearchConsolePages) | **GET** /search_console/pages | Top Search Console pages (Growth+) |
| [**getSearchConsoleQueries**](SearchConsoleApi.md#getSearchConsoleQueries) | **GET** /search_console/queries | Top Search Console queries (Growth+) |
| [**getSearchConsoleSummary**](SearchConsoleApi.md#getSearchConsoleSummary) | **GET** /search_console/summary | Search Console summary (Growth+) |
| [**getSearchConsoleTimeseries**](SearchConsoleApi.md#getSearchConsoleTimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+) |


<a id="getSearchConsolePages"></a>
# **getSearchConsolePages**
> getSearchConsolePages(projectId, range, from, to, sort, page, perPage, output, searchType, filters, dataState)

Top Search Console pages (Growth+)

Top Google Search Console landing pages over a date range, ranked by impressions, clicks, ctr or position, paginated. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts distinct keys available for the range: keys from synced daily rows for stored reads, or up to 25,000 rows from one Google request for live reads. Live responses include truncated: true when that limit is reached. Sorting and pagination apply to the available set.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SearchConsoleApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val sort : kotlin.String = sort_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
val searchType : kotlin.String = searchType_example // kotlin.String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
val filters : kotlin.String = [{"dimension":"page","operator":"contains","expression":"/blog/"}] // kotlin.String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
val dataState : kotlin.String = dataState_example // kotlin.String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
try {
    apiInstance.getSearchConsolePages(projectId, range, from, to, sort, page, perPage, output, searchType, filters, dataState)
} catch (e: ClientException) {
    println("4xx response calling SearchConsoleApi#getSearchConsolePages")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SearchConsoleApi#getSearchConsolePages")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **sort** | **kotlin.String**|  | [optional] [default to Sort.impressions] [enum: impressions, clicks, ctr, position] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **searchType** | **kotlin.String**| Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to SearchType.web] [enum: web, image, video, news, discover, googleNews] |
| **filters** | **kotlin.String**| Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dataState** | **kotlin.String**| final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to DataState.&#x60;final&#x60;] [enum: final, all] |

### Return type

null (empty response body)

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

<a id="getSearchConsoleQueries"></a>
# **getSearchConsoleQueries**
> getSearchConsoleQueries(projectId, range, from, to, sort, page, perPage, output, searchType, filters, dataState)

Top Search Console queries (Growth+)

Top Google Search Console search queries over a date range, ranked by impressions, clicks, ctr or position, paginated. Excludes anonymized queries; for headline totals use /search_console/summary. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts distinct keys available for the range: keys from synced daily rows for stored reads, or up to 25,000 rows from one Google request for live reads. Live responses include truncated: true when that limit is reached. Sorting and pagination apply to the available set.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SearchConsoleApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val sort : kotlin.String = sort_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
val searchType : kotlin.String = searchType_example // kotlin.String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
val filters : kotlin.String = [{"dimension":"page","operator":"contains","expression":"/blog/"}] // kotlin.String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
val dataState : kotlin.String = dataState_example // kotlin.String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
try {
    apiInstance.getSearchConsoleQueries(projectId, range, from, to, sort, page, perPage, output, searchType, filters, dataState)
} catch (e: ClientException) {
    println("4xx response calling SearchConsoleApi#getSearchConsoleQueries")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SearchConsoleApi#getSearchConsoleQueries")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **sort** | **kotlin.String**|  | [optional] [default to Sort.impressions] [enum: impressions, clicks, ctr, position] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **searchType** | **kotlin.String**| Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to SearchType.web] [enum: web, image, video, news, discover, googleNews] |
| **filters** | **kotlin.String**| Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dataState** | **kotlin.String**| final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to DataState.&#x60;final&#x60;] [enum: final, all] |

### Return type

null (empty response body)

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

<a id="getSearchConsoleSummary"></a>
# **getSearchConsoleSummary**
> getSearchConsoleSummary(projectId, range, from, to, dimension, limit, searchType, filters, dataState)

Search Console summary (Growth+)

Google Search Console headline totals (impressions, clicks, ctr as a 0..1 fraction, average position) for the project over a date range. Pass dimension&#x3D;country, device, page, query or searchAppearance to also receive the breakdown aggregated over the range, capped by limit. Requires the project to have a connected Search Console property and the Growth plan or above; otherwise returns ERR_SEARCH_CONSOLE_NOT_CONNECTED or ERR_PLAN_REQUIRED. X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SearchConsoleApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val dimension : kotlin.String = dimension_example // kotlin.String | Optional breakdown aggregated over the range. country and device are lowercased; page and query keep the casing Google returns, because a page URL is case sensitive.
val limit : kotlin.Int = 56 // kotlin.Int | Maximum breakdown rows, sorted by impressions descending. Default and maximum 1000. Use /search_console/queries or /search_console/pages to page through a full list.
val searchType : kotlin.String = searchType_example // kotlin.String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
val filters : kotlin.String = [{"dimension":"page","operator":"contains","expression":"/blog/"}] // kotlin.String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
val dataState : kotlin.String = dataState_example // kotlin.String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
try {
    apiInstance.getSearchConsoleSummary(projectId, range, from, to, dimension, limit, searchType, filters, dataState)
} catch (e: ClientException) {
    println("4xx response calling SearchConsoleApi#getSearchConsoleSummary")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SearchConsoleApi#getSearchConsoleSummary")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **dimension** | **kotlin.String**| Optional breakdown aggregated over the range. country and device are lowercased; page and query keep the casing Google returns, because a page URL is case sensitive. | [optional] [enum: country, device, page, query, searchAppearance] |
| **limit** | **kotlin.Int**| Maximum breakdown rows, sorted by impressions descending. Default and maximum 1000. Use /search_console/queries or /search_console/pages to page through a full list. | [optional] |
| **searchType** | **kotlin.String**| Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to SearchType.web] [enum: web, image, video, news, discover, googleNews] |
| **filters** | **kotlin.String**| Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dataState** | **kotlin.String**| final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to DataState.&#x60;final&#x60;] [enum: final, all] |

### Return type

null (empty response body)

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

<a id="getSearchConsoleTimeseries"></a>
# **getSearchConsoleTimeseries**
> getSearchConsoleTimeseries(projectId, range, from, to, granularity, output, searchType, filters, dataState)

Search Console time series (Growth+)

Google Search Console property-wide series (impressions, clicks, ctr, position) bucketed by day, week or month. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SearchConsoleApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val granularity : kotlin.String = granularity_example // kotlin.String | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
val searchType : kotlin.String = searchType_example // kotlin.String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
val filters : kotlin.String = [{"dimension":"page","operator":"contains","expression":"/blog/"}] // kotlin.String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
val dataState : kotlin.String = dataState_example // kotlin.String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
try {
    apiInstance.getSearchConsoleTimeseries(projectId, range, from, to, granularity, output, searchType, filters, dataState)
} catch (e: ClientException) {
    println("4xx response calling SearchConsoleApi#getSearchConsoleTimeseries")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SearchConsoleApi#getSearchConsoleTimeseries")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **searchType** | **kotlin.String**| Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to SearchType.web] [enum: web, image, video, news, discover, googleNews] |
| **filters** | **kotlin.String**| Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dataState** | **kotlin.String**| final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to DataState.&#x60;final&#x60;] [enum: final, all] |

### Return type

null (empty response body)

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

