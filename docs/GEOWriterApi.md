# GEOWriterApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createIntelligenceTask**](GEOWriterApi.md#createIntelligenceTask) | **POST** /intelligence_tasks | Create a GEO Writer task |
| [**getIntelligenceTask**](GEOWriterApi.md#getIntelligenceTask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task |
| [**listIntelligenceTasks**](GEOWriterApi.md#listIntelligenceTasks) | **GET** /intelligence_tasks | List GEO Writer tasks |
| [**revertIntelligenceTaskContent**](GEOWriterApi.md#revertIntelligenceTaskContent) | **POST** /intelligence_tasks/{id}/revert | Revert GEO Writer task content |
| [**updateIntelligenceTaskContent**](GEOWriterApi.md#updateIntelligenceTaskContent) | **PATCH** /intelligence_tasks/{id} | Edit GEO Writer task content |


<a id="createIntelligenceTask"></a>
# **createIntelligenceTask**
> IntelligenceTask createIntelligenceTask(intelligenceTaskCreateRequest)

Create a GEO Writer task

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOWriterApi()
val intelligenceTaskCreateRequest : IntelligenceTaskCreateRequest =  // IntelligenceTaskCreateRequest | 
try {
    val result : IntelligenceTask = apiInstance.createIntelligenceTask(intelligenceTaskCreateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOWriterApi#createIntelligenceTask")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOWriterApi#createIntelligenceTask")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **intelligenceTaskCreateRequest** | [**IntelligenceTaskCreateRequest**](IntelligenceTaskCreateRequest.md)|  | |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

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

<a id="getIntelligenceTask"></a>
# **getIntelligenceTask**
> IntelligenceTask getIntelligenceTask(id, projectId)

Get a GEO Writer task

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOWriterApi()
val id : kotlin.String = id_example // kotlin.String | Numeric task ID or public_id string token
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    val result : IntelligenceTask = apiInstance.getIntelligenceTask(id, projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOWriterApi#getIntelligenceTask")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOWriterApi#getIntelligenceTask")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**| Numeric task ID or public_id string token | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

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

<a id="listIntelligenceTasks"></a>
# **listIntelligenceTasks**
> listIntelligenceTasks(projectId, taskType, status, page, perPage)

List GEO Writer tasks

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOWriterApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val taskType : kotlin.String = taskType_example // kotlin.String | 
val status : kotlin.String = status_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    apiInstance.listIntelligenceTasks(projectId, taskType, status, page, perPage)
} catch (e: ClientException) {
    println("4xx response calling GEOWriterApi#listIntelligenceTasks")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOWriterApi#listIntelligenceTasks")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **taskType** | **kotlin.String**|  | [optional] [enum: brief, create, update, pr_insights, custom] |
| **status** | **kotlin.String**|  | [optional] |
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
 - **Accept**: Not defined

<a id="revertIntelligenceTaskContent"></a>
# **revertIntelligenceTaskContent**
> IntelligenceTask revertIntelligenceTaskContent(id, projectId)

Revert GEO Writer task content

Discards every manual edit on the task and restores the output exactly as it was generated. Returns ERR_INVALID_PARAM when the task has no manual edits. Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Writer.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOWriterApi()
val id : kotlin.String = id_example // kotlin.String | Numeric task ID or public_id string token
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    val result : IntelligenceTask = apiInstance.revertIntelligenceTaskContent(id, projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOWriterApi#revertIntelligenceTaskContent")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOWriterApi#revertIntelligenceTaskContent")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**| Numeric task ID or public_id string token | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

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

<a id="updateIntelligenceTaskContent"></a>
# **updateIntelligenceTaskContent**
> IntelligenceTaskUpdateResponse updateIntelligenceTaskContent(id, intelligenceTaskUpdateRequest)

Edit GEO Writer task content

Edits the text of a completed task in place. &#x60;edits&#x60; maps dotted paths into result_data (for example &#x60;title&#x60; or &#x60;sections.0.content&#x60;) to replacement text. Only string fields that already exist can change: a path that does not resolve to text, a blank &#x60;title&#x60;, a value over 20,000 characters or an empty &#x60;edits&#x60; object is rejected with ERR_INVALID_PARAM and nothing is written. Values identical to the stored text are ignored, and the response lists the paths that actually changed. The first edit keeps a copy of the generated output so POST /intelligence_tasks/{id}/revert can restore it; regenerating the task replaces the edited content. Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Writer.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOWriterApi()
val id : kotlin.String = id_example // kotlin.String | Numeric task ID or public_id string token
val intelligenceTaskUpdateRequest : IntelligenceTaskUpdateRequest =  // IntelligenceTaskUpdateRequest | 
try {
    val result : IntelligenceTaskUpdateResponse = apiInstance.updateIntelligenceTaskContent(id, intelligenceTaskUpdateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOWriterApi#updateIntelligenceTaskContent")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOWriterApi#updateIntelligenceTaskContent")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**| Numeric task ID or public_id string token | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **intelligenceTaskUpdateRequest** | [**IntelligenceTaskUpdateRequest**](IntelligenceTaskUpdateRequest.md)|  | |

### Return type

[**IntelligenceTaskUpdateResponse**](IntelligenceTaskUpdateResponse.md)

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

