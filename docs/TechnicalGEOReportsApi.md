# TechnicalGEOReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createTechnicalGeoReports**](TechnicalGEOReportsApi.md#createTechnicalGeoReports) | **POST** /technical_geo_reports | Run technical GEO analysis |
| [**getTechnicalGeoReport**](TechnicalGEOReportsApi.md#getTechnicalGeoReport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report |
| [**listTechnicalGeoReports**](TechnicalGEOReportsApi.md#listTechnicalGeoReports) | **GET** /technical_geo_reports | List technical GEO reports |


<a id="createTechnicalGeoReports"></a>
# **createTechnicalGeoReports**
> createTechnicalGeoReports(createTechnicalGeoReportsRequest)

Run technical GEO analysis

Launches the full technical GEO analysis bundle (crawlability, schema, content readiness, discoverability, site structure, robots.txt, agent readiness, llms.txt, AI visibility) for a URL + country. Each report runs in a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = TechnicalGEOReportsApi()
val createTechnicalGeoReportsRequest : CreateTechnicalGeoReportsRequest =  // CreateTechnicalGeoReportsRequest | 
try {
    apiInstance.createTechnicalGeoReports(createTechnicalGeoReportsRequest)
} catch (e: ClientException) {
    println("4xx response calling TechnicalGEOReportsApi#createTechnicalGeoReports")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling TechnicalGEOReportsApi#createTechnicalGeoReports")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createTechnicalGeoReportsRequest** | [**CreateTechnicalGeoReportsRequest**](CreateTechnicalGeoReportsRequest.md)|  | |

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

 - **Content-Type**: application/json
 - **Accept**: application/json

<a id="getTechnicalGeoReport"></a>
# **getTechnicalGeoReport**
> getTechnicalGeoReport(id, projectId, reportType)

Get a technical GEO report

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again. Summaries carry output_language_code (the ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report left on the website&#39;s own language in the app, and for every other report type); a completed llms_txt result_data also returns manually_edited_at, original_llms_txt_content and original_llms_full_txt_content (the generated files, set once the customer edited the files in the app) and metadata.output_language_code.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = TechnicalGEOReportsApi()
val id : kotlin.Int = 56 // kotlin.Int | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val reportType : kotlin.String = reportType_example // kotlin.String | 
try {
    apiInstance.getTechnicalGeoReport(id, projectId, reportType)
} catch (e: ClientException) {
    println("4xx response calling TechnicalGEOReportsApi#getTechnicalGeoReport")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling TechnicalGEOReportsApi#getTechnicalGeoReport")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |
| **projectId** | **kotlin.Int**| Project ID | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **reportType** | **kotlin.String**|  | [enum: crawlability, schema, content_readiness, discoverability, site_structure, robots_txt, agent_readiness, llms_txt, ai_visibility] |

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

<a id="listTechnicalGeoReports"></a>
# **listTechnicalGeoReports**
> listTechnicalGeoReports(projectId, reportType, status, batchId, page, perPage)

List technical GEO reports

Lists reports of one technical GEO type for a project, newest first. Use agent_readiness for the AI/Agent Readiness report.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = TechnicalGEOReportsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val reportType : kotlin.String = reportType_example // kotlin.String | 
val status : kotlin.String = status_example // kotlin.String | Optional status filter; valid values depend on report_type
val batchId : kotlin.Int = 56 // kotlin.Int | Optional batch id returned when the report bundle was created
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    apiInstance.listTechnicalGeoReports(projectId, reportType, status, batchId, page, perPage)
} catch (e: ClientException) {
    println("4xx response calling TechnicalGEOReportsApi#listTechnicalGeoReports")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling TechnicalGEOReportsApi#listTechnicalGeoReports")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **reportType** | **kotlin.String**|  | [enum: crawlability, schema, content_readiness, discoverability, site_structure, robots_txt, agent_readiness, llms_txt, ai_visibility] |
| **status** | **kotlin.String**| Optional status filter; valid values depend on report_type | [optional] |
| **batchId** | **kotlin.Int**| Optional batch id returned when the report bundle was created | [optional] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |

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

