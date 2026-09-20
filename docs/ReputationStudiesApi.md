# ReputationStudiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getReputationReport**](ReputationStudiesApi.md#getReputationReport) | **GET** /reputation/reports/{id} | Get reputation report scores |
| [**getStudy**](ReputationStudiesApi.md#getStudy) | **GET** /studies/{id} | Get a custom AI study |
| [**getStudyReport**](ReputationStudiesApi.md#getStudyReport) | **GET** /studies/{id}/reports/{report_id} | Get custom study report scores |
| [**listReputationReports**](ReputationStudiesApi.md#listReputationReports) | **GET** /reputation/reports | List reputation reports |
| [**listStudies**](ReputationStudiesApi.md#listStudies) | **GET** /studies | List custom AI studies |


<a id="getReputationReport"></a>
# **getReputationReport**
> getReputationReport(id, projectId, page, perPage, model, brand, dimension, output)

Get reputation report scores

One reputation report&#39;s scores as flat rows: one row per analyst model, brand, dimension and attribute, with its 0-100 score and the reasoning the model gave. Scores come from several analyst models independently, so compare models rather than averaging them blindly.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ReputationStudiesApi()
val id : kotlin.String = id_example // kotlin.String | The report id from GET /reputation/reports
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val model : kotlin.String = model_example // kotlin.String | Restrict to one analyst model
val brand : kotlin.String = brand_example // kotlin.String | Restrict to one brand name, or a comma-separated list
val dimension : kotlin.String = dimension_example // kotlin.String | Restrict to one reputation dimension key
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.getReputationReport(id, projectId, page, perPage, model, brand, dimension, output)
} catch (e: ClientException) {
    println("4xx response calling ReputationStudiesApi#getReputationReport")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ReputationStudiesApi#getReputationReport")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**| The report id from GET /reputation/reports | |
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **model** | **kotlin.String**| Restrict to one analyst model | [optional] [enum: chatgpt, perplexity, gemini, deepseek, grok, claude] |
| **brand** | **kotlin.String**| Restrict to one brand name, or a comma-separated list | [optional] |
| **dimension** | **kotlin.String**| Restrict to one reputation dimension key | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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

<a id="getStudy"></a>
# **getStudy**
> getStudy(id)

Get a custom AI study

One study with its brief, the subjects it compares, the dimensions it scores them on, and its report history. Use the ids in &#x60;reports&#x60; with GET /studies/{id}/reports/{report_id}.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ReputationStudiesApi()
val id : kotlin.Int = 56 // kotlin.Int | 
try {
    apiInstance.getStudy(id)
} catch (e: ClientException) {
    println("4xx response calling ReputationStudiesApi#getStudy")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ReputationStudiesApi#getStudy")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int**|  | |

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

<a id="getStudyReport"></a>
# **getStudyReport**
> getStudyReport(id, reportId, page, perPage, model, subject, dimension, output)

Get custom study report scores

One custom-study report&#39;s scores as flat rows: one row per analyst model, subject, dimension and attribute, with its 0-100 score and the reasoning the model gave.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ReputationStudiesApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val reportId : kotlin.String = reportId_example // kotlin.String | The report id from GET /studies/{id}
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val model : kotlin.String = model_example // kotlin.String | Restrict to one analyst model
val subject : kotlin.String = subject_example // kotlin.String | Restrict to one subject name, or a comma-separated list
val dimension : kotlin.String = dimension_example // kotlin.String | Restrict to one dimension key
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.getStudyReport(id, reportId, page, perPage, model, subject, dimension, output)
} catch (e: ClientException) {
    println("4xx response calling ReputationStudiesApi#getStudyReport")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ReputationStudiesApi#getStudyReport")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| **reportId** | **kotlin.String**| The report id from GET /studies/{id} | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **model** | **kotlin.String**| Restrict to one analyst model | [optional] [enum: chatgpt, perplexity, gemini, deepseek, grok, claude] |
| **subject** | **kotlin.String**| Restrict to one subject name, or a comma-separated list | [optional] |
| **dimension** | **kotlin.String**| Restrict to one dimension key | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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

<a id="listReputationReports"></a>
# **listReputationReports**
> listReputationReports(projectId, page, perPage, output)

List reputation reports

The monthly multi-model analyst reports scoring the tracked brand and its competitors, newest first. Pending and failed reports are included on purpose: whether this month ran at all is often the question. Each row carries the report id, its status, and which analyst models produced data. Requires reputation monitoring to be enabled on the account.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ReputationStudiesApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listReputationReports(projectId, page, perPage, output)
} catch (e: ClientException) {
    println("4xx response calling ReputationStudiesApi#listReputationReports")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ReputationStudiesApi#listReputationReports")
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
 - **Accept**: Not defined

<a id="listStudies"></a>
# **listStudies**
> listStudies(projectId, status, page, perPage, output)

List custom AI studies

The custom AI studies defined on the account: analyst reports over any set of subjects (brands, sectors, topics) and any set of dimensions. Studies belong to the ACCOUNT, not to a project, so project_id is an optional filter here and account-level studies are returned whichever project you filter by. A team member whose project access is restricted sees only the studies of the projects they can reach. Requires reputation monitoring to be enabled on the account.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ReputationStudiesApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Restrict to studies attached to this project (plus account-level ones)
val status : kotlin.String = status_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listStudies(projectId, status, page, perPage, output)
} catch (e: ClientException) {
    println("4xx response calling ReputationStudiesApi#listStudies")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ReputationStudiesApi#listStudies")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Restrict to studies attached to this project (plus account-level ones) | [optional] |
| **status** | **kotlin.String**|  | [optional] [enum: active, archived] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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
 - **Accept**: Not defined

