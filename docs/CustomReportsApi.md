# CustomReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getCustomReport**](CustomReportsApi.md#getCustomReport) | **GET** /custom_reports/{id} | Get a custom report with its widget data |
| [**listCustomReports**](CustomReportsApi.md#listCustomReports) | **GET** /custom_reports | List custom reports |
| [**sendCustomReport**](CustomReportsApi.md#sendCustomReport) | **POST** /custom_reports/{id}/send | Send a custom report now |


<a id="getCustomReport"></a>
# **getCustomReport**
> CustomReportDetailResponse getCustomReport(id, projectId)

Get a custom report with its widget data

The configuration of one custom report (date range, filters, schedule, layout) and the data of every widget computed for today, the same numbers the report page, its shared link and its PDF show. Each widget carries its &#x60;kind&#x60; and a &#x60;data&#x60; object shaped by it: &#x60;series&#x60; for &#x60;timeseries&#x60;, &#x60;slices&#x60; for &#x60;donut&#x60;, &#x60;bars&#x60; for &#x60;bar&#x60;, &#x60;values&#x60; and &#x60;changes&#x60; for &#x60;kpi_grid&#x60;, &#x60;rows&#x60; for &#x60;table&#x60;. A widget whose data source is not connected has &#x60;available: false&#x60; and &#x60;data: null&#x60;. Nothing is saved or sent. Requires the Scale plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CustomReportsApi()
val id : kotlin.Int = 56 // kotlin.Int | Custom report id, from GET /custom_reports
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    val result : CustomReportDetailResponse = apiInstance.getCustomReport(id, projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling CustomReportsApi#getCustomReport")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CustomReportsApi#getCustomReport")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**| Custom report id, from GET /custom_reports | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

### Return type

[**CustomReportDetailResponse**](CustomReportDetailResponse.md)

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

<a id="listCustomReports"></a>
# **listCustomReports**
> CustomReportsResponse listCustomReports(projectId, page, perPage, output)

List custom reports

The custom reports of the project, newest first, as the Reports &gt; Custom Reports list shows them. Recipient addresses, the shared-link token and the password are never returned. Requires the Scale plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CustomReportsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : CustomReportsResponse = apiInstance.listCustomReports(projectId, page, perPage, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling CustomReportsApi#listCustomReports")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CustomReportsApi#listCustomReports")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**CustomReportsResponse**](CustomReportsResponse.md)

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

<a id="sendCustomReport"></a>
# **sendCustomReport**
> CustomReportSendResponse sendCustomReport(id, sendCustomReportRequest)

Send a custom report now

Queues the report&#39;s PDF for its recipients, like the Send now button on the report page: the report must be published and have at least one recipient (ERR_INVALID_PARAM otherwise), and each report can be sent once every 10 minutes (429 ERR_RATE_LIMITED with Retry-After). Not available from a white-label portal or for a report made inside one (ERR_INTEGRATION_UNAVAILABLE). Requires the Scale plan or above, a &#x60;read_write&#x60; scope API key and, for team members, update permission on Custom Reports.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CustomReportsApi()
val id : kotlin.Int = 56 // kotlin.Int | Custom report id, from GET /custom_reports
val sendCustomReportRequest : SendCustomReportRequest =  // SendCustomReportRequest | 
try {
    val result : CustomReportSendResponse = apiInstance.sendCustomReport(id, sendCustomReportRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling CustomReportsApi#sendCustomReport")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CustomReportsApi#sendCustomReport")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**| Custom report id, from GET /custom_reports | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **sendCustomReportRequest** | [**SendCustomReportRequest**](SendCustomReportRequest.md)|  | |

### Return type

[**CustomReportSendResponse**](CustomReportSendResponse.md)

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

 - **Content-Type**: application/json
 - **Accept**: application/json

