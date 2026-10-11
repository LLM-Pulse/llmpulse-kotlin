# SearchConsoleApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getSearchConsolePages**](SearchConsoleApi.md#getSearchConsolePages) | **GET** /search_console/pages | Top Search Console pages (Growth+) |
| [**getSearchConsoleQueries**](SearchConsoleApi.md#getSearchConsoleQueries) | **GET** /search_console/queries | Top Search Console queries (Growth+) |
| [**getSearchConsoleRows**](SearchConsoleApi.md#getSearchConsoleRows) | **GET** /search_console/rows | Search Console rows by several dimensions (Growth+) |
| [**getSearchConsoleSummary**](SearchConsoleApi.md#getSearchConsoleSummary) | **GET** /search_console/summary | Search Console summary (Growth+) |
| [**getSearchConsoleTimeseries**](SearchConsoleApi.md#getSearchConsoleTimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+) |


<a id="getSearchConsolePages"></a>
# **getSearchConsolePages**
> SearchConsoleListResponse getSearchConsolePages(projectId, range, from, to, sort, page, perPage, startRow, output, searchType, filters, dataState, aggregationType)

Top Search Console pages (Growth+)

Top Google Search Console landing pages over a date range, ranked by impressions, clicks, ctr or position, paginated. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, and start_row reads the next block. Page rows are counted per page rather than per property, so they can differ from the totals. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SearchConsoleApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | Start date (YYYY-MM-DD). Defaults to 30 days ago.
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
val sort : kotlin.String = sort_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val startRow : kotlin.Int = 56 // kotlin.Int | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
val searchType : kotlin.String = searchType_example // kotlin.String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
val filters : kotlin.String = [{"dimension":"page","operator":"contains","expression":"/blog/"}] // kotlin.String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
val dataState : kotlin.String = dataState_example // kotlin.String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
val aggregationType : kotlin.String = aggregationType_example // kotlin.String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
try {
    val result : SearchConsoleListResponse = apiInstance.getSearchConsolePages(projectId, range, from, to, sort, page, perPage, startRow, output, searchType, filters, dataState, aggregationType)
    println(result)
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
| **range** | **kotlin.Int**| Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **java.time.LocalDate**| Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **java.time.LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **sort** | **kotlin.String**|  | [optional] [default to Sort.impressions] [enum: impressions, clicks, ctr, position] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **startRow** | **kotlin.Int**| Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [optional] [default to 0] |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **searchType** | **kotlin.String**| Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to SearchType.web] [enum: web, image, video, news, discover, googleNews] |
| **filters** | **kotlin.String**| Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **dataState** | **kotlin.String**| final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to DataState.&#x60;final&#x60;] [enum: final, all] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **aggregationType** | **kotlin.String**| How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional] [default to AggregationType.auto] [enum: auto, byPage, byProperty] |

### Return type

[**SearchConsoleListResponse**](SearchConsoleListResponse.md)

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
> SearchConsoleListResponse getSearchConsoleQueries(projectId, range, from, to, sort, page, perPage, startRow, output, searchType, filters, dataState, aggregationType)

Top Search Console queries (Growth+)

Top Google Search Console search queries over a date range, ranked by impressions, clicks, ctr or position, paginated. Excludes anonymized queries; for headline totals use /search_console/summary. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, so the rows add up to less than the totals, and start_row reads the next block. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SearchConsoleApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | Start date (YYYY-MM-DD). Defaults to 30 days ago.
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
val sort : kotlin.String = sort_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val startRow : kotlin.Int = 56 // kotlin.Int | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
val searchType : kotlin.String = searchType_example // kotlin.String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
val filters : kotlin.String = [{"dimension":"page","operator":"contains","expression":"/blog/"}] // kotlin.String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
val dataState : kotlin.String = dataState_example // kotlin.String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
val aggregationType : kotlin.String = aggregationType_example // kotlin.String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
try {
    val result : SearchConsoleListResponse = apiInstance.getSearchConsoleQueries(projectId, range, from, to, sort, page, perPage, startRow, output, searchType, filters, dataState, aggregationType)
    println(result)
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
| **range** | **kotlin.Int**| Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **java.time.LocalDate**| Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **java.time.LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **sort** | **kotlin.String**|  | [optional] [default to Sort.impressions] [enum: impressions, clicks, ctr, position] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **startRow** | **kotlin.Int**| Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [optional] [default to 0] |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **searchType** | **kotlin.String**| Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to SearchType.web] [enum: web, image, video, news, discover, googleNews] |
| **filters** | **kotlin.String**| Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **dataState** | **kotlin.String**| final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to DataState.&#x60;final&#x60;] [enum: final, all] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **aggregationType** | **kotlin.String**| How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional] [default to AggregationType.auto] [enum: auto, byPage, byProperty] |

### Return type

[**SearchConsoleListResponse**](SearchConsoleListResponse.md)

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

<a id="getSearchConsoleRows"></a>
# **getSearchConsoleRows**
> SearchConsoleRowsResponse getSearchConsoleRows(projectId, dimensions, range, from, to, sort, page, perPage, startRow, output, searchType, filters, dataState, aggregationType)

Search Console rows by several dimensions (Growth+)

Google Search Console rows grouped by 1 to 3 dimensions (date, country, device, page, query, searchAppearance) over a date range, each row carrying its dimension values as fields plus impressions, clicks, ctr (0..1) and position, ranked by impressions, clicks, ctr or position, paginated. Google ranks rows by clicks and returns at most 25,000 per request (truncated: true when reached); start_row moves that window. Query rows exclude anonymized queries, so rows add up to less than the summary totals. Requires a connected Search Console property (Growth+) and live reads: stored reads return ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access and ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. A combination Google refuses comes back as ERR_INVALID_PARAM with its reason.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SearchConsoleApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val dimensions : kotlin.String = page,query // kotlin.String | Comma-separated dimensions to group by, 1 to 3 of date, country, device, page, query, searchAppearance. Each becomes a field of every row; country and device values are lowercase.
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | Start date (YYYY-MM-DD). Defaults to 30 days ago.
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
val sort : kotlin.String = sort_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val startRow : kotlin.Int = 56 // kotlin.Int | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
val searchType : kotlin.String = searchType_example // kotlin.String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
val filters : kotlin.String = [{"dimension":"page","operator":"contains","expression":"/blog/"}] // kotlin.String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
val dataState : kotlin.String = dataState_example // kotlin.String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
val aggregationType : kotlin.String = aggregationType_example // kotlin.String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
try {
    val result : SearchConsoleRowsResponse = apiInstance.getSearchConsoleRows(projectId, dimensions, range, from, to, sort, page, perPage, startRow, output, searchType, filters, dataState, aggregationType)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling SearchConsoleApi#getSearchConsoleRows")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SearchConsoleApi#getSearchConsoleRows")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **dimensions** | **kotlin.String**| Comma-separated dimensions to group by, 1 to 3 of date, country, device, page, query, searchAppearance. Each becomes a field of every row; country and device values are lowercase. | |
| **range** | **kotlin.Int**| Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **java.time.LocalDate**| Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **java.time.LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **sort** | **kotlin.String**|  | [optional] [default to Sort.impressions] [enum: impressions, clicks, ctr, position] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **startRow** | **kotlin.Int**| Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [optional] [default to 0] |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **searchType** | **kotlin.String**| Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to SearchType.web] [enum: web, image, video, news, discover, googleNews] |
| **filters** | **kotlin.String**| Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **dataState** | **kotlin.String**| final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to DataState.&#x60;final&#x60;] [enum: final, all] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **aggregationType** | **kotlin.String**| How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional] [default to AggregationType.auto] [enum: auto, byPage, byProperty] |

### Return type

[**SearchConsoleRowsResponse**](SearchConsoleRowsResponse.md)

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
> SearchConsoleSummaryResponse getSearchConsoleSummary(projectId, range, from, to, dimension, limit, searchType, filters, dataState, aggregationType)

Search Console summary (Growth+)

Google Search Console headline totals (impressions, clicks, ctr as a 0..1 fraction, average position) for the project over a date range. Pass dimension&#x3D;country, device, page, query or searchAppearance to also receive the breakdown aggregated over the range, capped by limit. With filters and no dimension, totals are the complete figure Google reports for that filter. Breakdown rows are capped by limit and by Google&#39;s 25,000-row maximum; breakdown_truncated: true means rows were left out. Query rows exclude anonymized queries, and page and searchAppearance rows are counted per page rather than per property, so breakdown rows can differ from the totals. Requires the project to have a connected Search Console property and the Growth plan or above; otherwise returns ERR_SEARCH_CONSOLE_NOT_CONNECTED or ERR_PLAN_REQUIRED. X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SearchConsoleApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | Start date (YYYY-MM-DD). Defaults to 30 days ago.
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
val dimension : kotlin.String = dimension_example // kotlin.String | Optional breakdown aggregated over the range. country and device are lowercased; page and query keep the casing Google returns, because a page URL is case sensitive.
val limit : kotlin.Int = 56 // kotlin.Int | Maximum breakdown rows, sorted by impressions descending. Default and maximum 1000. Use /search_console/queries or /search_console/pages to page through up to 25,000 rows.
val searchType : kotlin.String = searchType_example // kotlin.String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
val filters : kotlin.String = [{"dimension":"page","operator":"contains","expression":"/blog/"}] // kotlin.String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
val dataState : kotlin.String = dataState_example // kotlin.String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
val aggregationType : kotlin.String = aggregationType_example // kotlin.String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
try {
    val result : SearchConsoleSummaryResponse = apiInstance.getSearchConsoleSummary(projectId, range, from, to, dimension, limit, searchType, filters, dataState, aggregationType)
    println(result)
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
| **range** | **kotlin.Int**| Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **java.time.LocalDate**| Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **java.time.LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **dimension** | **kotlin.String**| Optional breakdown aggregated over the range. country and device are lowercased; page and query keep the casing Google returns, because a page URL is case sensitive. | [optional] [enum: country, device, page, query, searchAppearance] |
| **limit** | **kotlin.Int**| Maximum breakdown rows, sorted by impressions descending. Default and maximum 1000. Use /search_console/queries or /search_console/pages to page through up to 25,000 rows. | [optional] |
| **searchType** | **kotlin.String**| Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to SearchType.web] [enum: web, image, video, news, discover, googleNews] |
| **filters** | **kotlin.String**| Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **dataState** | **kotlin.String**| final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to DataState.&#x60;final&#x60;] [enum: final, all] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **aggregationType** | **kotlin.String**| How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional] [default to AggregationType.auto] [enum: auto, byPage, byProperty] |

### Return type

[**SearchConsoleSummaryResponse**](SearchConsoleSummaryResponse.md)

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
> SearchConsoleTimeseriesResponse getSearchConsoleTimeseries(projectId, range, from, to, granularity, output, searchType, filters, dataState, aggregationType)

Search Console time series (Growth+)

Google Search Console series (impressions, clicks, ctr, position) bucketed by day, week or month, property-wide unless filters narrows it. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SearchConsoleApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | Start date (YYYY-MM-DD). Defaults to 30 days ago.
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
val granularity : kotlin.String = granularity_example // kotlin.String | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
val searchType : kotlin.String = searchType_example // kotlin.String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
val filters : kotlin.String = [{"dimension":"page","operator":"contains","expression":"/blog/"}] // kotlin.String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
val dataState : kotlin.String = dataState_example // kotlin.String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
val aggregationType : kotlin.String = aggregationType_example // kotlin.String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
try {
    val result : SearchConsoleTimeseriesResponse = apiInstance.getSearchConsoleTimeseries(projectId, range, from, to, granularity, output, searchType, filters, dataState, aggregationType)
    println(result)
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
| **range** | **kotlin.Int**| Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **java.time.LocalDate**| Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **java.time.LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **searchType** | **kotlin.String**| Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to SearchType.web] [enum: web, image, video, news, discover, googleNews] |
| **filters** | **kotlin.String**| Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **dataState** | **kotlin.String**| final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to DataState.&#x60;final&#x60;] [enum: final, all] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **aggregationType** | **kotlin.String**| How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional] [default to AggregationType.auto] [enum: auto, byPage, byProperty] |

### Return type

[**SearchConsoleTimeseriesResponse**](SearchConsoleTimeseriesResponse.md)

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

