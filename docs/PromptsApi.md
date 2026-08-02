# PromptsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**assignPromptTags**](PromptsApi.md#assignPromptTags) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts |
| [**createPrompts**](PromptsApi.md#createPrompts) | **POST** /prompts | Bulk-create prompts |
| [**deletePrompt**](PromptsApi.md#deletePrompt) | **DELETE** /prompts/{id} | Delete a prompt |


<a id="assignPromptTags"></a>
# **assignPromptTags**
> assignPromptTags(assignPromptTagsRequest)

Bulk-attach tags to prompts

Idempotent bulk assignment of tags (Collections) to existing prompts. Tags can be resolved by id or by name (case-insensitive). Use &#x60;create_missing: true&#x60; to auto-create unknown tag names. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val assignPromptTagsRequest : AssignPromptTagsRequest =  // AssignPromptTagsRequest | 
try {
    apiInstance.assignPromptTags(assignPromptTagsRequest)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#assignPromptTags")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#assignPromptTags")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **assignPromptTagsRequest** | [**AssignPromptTagsRequest**](AssignPromptTagsRequest.md)|  | |

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

<a id="createPrompts"></a>
# **createPrompts**
> PromptsCreateResponse createPrompts(promptsCreateRequest)

Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val promptsCreateRequest : PromptsCreateRequest =  // PromptsCreateRequest | 
try {
    val result : PromptsCreateResponse = apiInstance.createPrompts(promptsCreateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#createPrompts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#createPrompts")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **promptsCreateRequest** | [**PromptsCreateRequest**](PromptsCreateRequest.md)|  | |

### Return type

[**PromptsCreateResponse**](PromptsCreateResponse.md)

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

<a id="deletePrompt"></a>
# **deletePrompt**
> deletePrompt(id, projectId)

Delete a prompt

Deletes a prompt (irreversible). The prompt disappears immediately and frees a prompt slot; its historical data (executions, mentions, citations, sentiment) is purged by a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.deletePrompt(id, projectId)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#deletePrompt")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#deletePrompt")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

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

