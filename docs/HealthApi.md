# HealthApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**ping**](HealthApi.md#ping) | **GET** /ping | Health check |


<a id="ping"></a>
# **ping**
> Ping200Response ping(projectId)

Health check

Validates the API key and optionally pings a project. Returns the authenticated user_id, project (if project_id is supplied), and a request_id.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = HealthApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Optional project to verify access for
try {
    val result : Ping200Response = apiInstance.ping(projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling HealthApi#ping")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling HealthApi#ping")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Optional project to verify access for | [optional] |

### Return type

[**Ping200Response**](Ping200Response.md)

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

