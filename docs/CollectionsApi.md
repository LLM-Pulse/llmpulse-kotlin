# CollectionsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCollection**](CollectionsApi.md#createCollection) | **POST** /collections | Create a tag |
| [**deleteCollection**](CollectionsApi.md#deleteCollection) | **DELETE** /collections/{id} | Delete a tag |
| [**updateCollection**](CollectionsApi.md#updateCollection) | **PATCH** /collections/{id} | Update a tag |


<a id="createCollection"></a>
# **createCollection**
> createCollection(createCollectionRequest)

Create a tag

Creates a tag (Collection) in a project. Optional &#x60;prompt_ids&#x60; attaches existing prompts in the same call. Tag name must be unique per project (case-insensitive). Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CollectionsApi()
val createCollectionRequest : CreateCollectionRequest =  // CreateCollectionRequest | 
try {
    apiInstance.createCollection(createCollectionRequest)
} catch (e: ClientException) {
    println("4xx response calling CollectionsApi#createCollection")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CollectionsApi#createCollection")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createCollectionRequest** | [**CreateCollectionRequest**](CreateCollectionRequest.md)|  | |

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

<a id="deleteCollection"></a>
# **deleteCollection**
> deleteCollection(id, projectId)

Delete a tag

Deletes a tag/collection. The prompts inside it are NOT deleted; only the grouping disappears. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CollectionsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.deleteCollection(id, projectId)
} catch (e: ClientException) {
    println("4xx response calling CollectionsApi#deleteCollection")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CollectionsApi#deleteCollection")
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

<a id="updateCollection"></a>
# **updateCollection**
> updateCollection(id, updateCollectionRequest)

Update a tag

Renames a tag/collection or changes its description. Prompt membership is managed via POST /prompts/assign_tags, not here. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CollectionsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val updateCollectionRequest : UpdateCollectionRequest =  // UpdateCollectionRequest | 
try {
    apiInstance.updateCollection(id, updateCollectionRequest)
} catch (e: ClientException) {
    println("4xx response calling CollectionsApi#updateCollection")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CollectionsApi#updateCollection")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updateCollectionRequest** | [**UpdateCollectionRequest**](UpdateCollectionRequest.md)|  | |

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

