# TechnicalGEOReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createTechnicalGeoReports**](TechnicalGEOReportsApi.md#createTechnicalGeoReports) | **POST** /technical_geo_reports | Run technical GEO analysis |
| [**getTechnicalGeoReport**](TechnicalGEOReportsApi.md#getTechnicalGeoReport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report |
| [**listTechnicalGeoReports**](TechnicalGEOReportsApi.md#listTechnicalGeoReports) | **GET** /technical_geo_reports | List technical GEO reports |
| [**revertTechnicalGeoReportContent**](TechnicalGEOReportsApi.md#revertTechnicalGeoReportContent) | **POST** /technical_geo_reports/{id}/revert_content | Revert llms.txt report content |
| [**updateTechnicalGeoReportContent**](TechnicalGEOReportsApi.md#updateTechnicalGeoReportContent) | **PATCH** /technical_geo_reports/{id}/content | Edit llms.txt report content |


<a id="createTechnicalGeoReports"></a>
# **createTechnicalGeoReports**
> createTechnicalGeoReports(createTechnicalGeoReportsRequest)

Run technical GEO analysis

Launches the full nine-report technical GEO analysis bundle for a URL + country. The bundle starts only when at least nine daily units remain. Each successfully created report uses one unit; a report that is not created uses none. Daily allocations vary by account. Each report runs in a background job. Requires a &#x60;read_write&#x60; scope API key.

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

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again. Summaries carry output_language_code (the ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website&#39;s own language, requested as auto or chosen in the app, and for every other report type); a completed llms_txt result_data also returns content_version (send it back to PATCH /technical_geo_reports/{id}/content), manually_edited_at, original_llms_txt_content and original_llms_full_txt_content (the generated files, kept from the first manual edit in the app, the API or MCP) and metadata.output_language_code.

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

<a id="revertTechnicalGeoReportContent"></a>
# **revertTechnicalGeoReportContent**
> LlmsTxtTechnicalGeoReport revertTechnicalGeoReportContent(id, technicalGeoReportContentRevertRequest)

Revert llms.txt report content

Discards every manual edit on the llms_txt report and restores the llms.txt and llms-full.txt files exactly as they were generated. Returns ERR_INVALID_PARAM when the report has no manual edits or report_type is not llms_txt. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on GEO Optimization.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = TechnicalGEOReportsApi()
val id : kotlin.Int = 56 // kotlin.Int | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
val technicalGeoReportContentRevertRequest : TechnicalGeoReportContentRevertRequest =  // TechnicalGeoReportContentRevertRequest | 
try {
    val result : LlmsTxtTechnicalGeoReport = apiInstance.revertTechnicalGeoReportContent(id, technicalGeoReportContentRevertRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling TechnicalGEOReportsApi#revertTechnicalGeoReportContent")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling TechnicalGEOReportsApi#revertTechnicalGeoReportContent")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **technicalGeoReportContentRevertRequest** | [**TechnicalGeoReportContentRevertRequest**](TechnicalGeoReportContentRevertRequest.md)|  | |

### Return type

[**LlmsTxtTechnicalGeoReport**](LlmsTxtTechnicalGeoReport.md)

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

<a id="updateTechnicalGeoReportContent"></a>
# **updateTechnicalGeoReportContent**
> TechnicalGeoReportContentUpdateResponse updateTechnicalGeoReportContent(id, technicalGeoReportContentUpdateRequest)

Edit llms.txt report content

Replaces the llms.txt and llms-full.txt files of a completed llms_txt report in place, without generating them again. &#x60;edits&#x60; maps llms_txt and/or llms_full_txt to the full replacement text. &#x60;content_version&#x60; must equal result_data.content_version of the report as last read; when the report changed since, the edit is refused as stale and the message names the current version. A missing or stale content_version, a blank file, a file over 200,000 characters, a value that is not text, an unknown file key, an empty &#x60;edits&#x60; object, a report that has not completed or a report_type other than llms_txt is rejected with ERR_INVALID_PARAM and nothing is written. Files are stored with Unix line endings and one trailing newline. A file identical to the stored one is ignored, and the response lists the files that actually changed. The first edit keeps the generated files in original_llms_txt_content and original_llms_full_txt_content so POST /technical_geo_reports/{id}/revert_content can restore them; running the report again creates a new report without these edits. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on GEO Optimization.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = TechnicalGEOReportsApi()
val id : kotlin.Int = 56 // kotlin.Int | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
val technicalGeoReportContentUpdateRequest : TechnicalGeoReportContentUpdateRequest =  // TechnicalGeoReportContentUpdateRequest | 
try {
    val result : TechnicalGeoReportContentUpdateResponse = apiInstance.updateTechnicalGeoReportContent(id, technicalGeoReportContentUpdateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling TechnicalGEOReportsApi#updateTechnicalGeoReportContent")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling TechnicalGEOReportsApi#updateTechnicalGeoReportContent")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **technicalGeoReportContentUpdateRequest** | [**TechnicalGeoReportContentUpdateRequest**](TechnicalGeoReportContentUpdateRequest.md)|  | |

### Return type

[**TechnicalGeoReportContentUpdateResponse**](TechnicalGeoReportContentUpdateResponse.md)

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

