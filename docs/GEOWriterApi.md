# GEOWriterApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createIntelligenceTask**](GEOWriterApi.md#createIntelligenceTask) | **POST** /intelligence_tasks | Create a GEO Writer task |
| [**getIntelligenceTask**](GEOWriterApi.md#getIntelligenceTask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task |
| [**listIntelligenceTasks**](GEOWriterApi.md#listIntelligenceTasks) | **GET** /intelligence_tasks | List GEO Writer tasks |


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

