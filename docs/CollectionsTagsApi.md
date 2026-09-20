# CollectionsTagsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**assignPromptTags**](CollectionsTagsApi.md#assignPromptTags) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts |
| [**createCollection**](CollectionsTagsApi.md#createCollection) | **POST** /collections | Create a tag |
| [**deleteCollection**](CollectionsTagsApi.md#deleteCollection) | **DELETE** /collections/{id} | Delete a tag |
| [**listCollections**](CollectionsTagsApi.md#listCollections) | **GET** /dimensions/collections | List tags/collections |
| [**listTags**](CollectionsTagsApi.md#listTags) | **GET** /dimensions/tags | List tags (alias for /collections) |
| [**updateCollection**](CollectionsTagsApi.md#updateCollection) | **PATCH** /collections/{id} | Update a tag |


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

val apiInstance = CollectionsTagsApi()
val assignPromptTagsRequest : AssignPromptTagsRequest =  // AssignPromptTagsRequest | 
try {
    apiInstance.assignPromptTags(assignPromptTagsRequest)
} catch (e: ClientException) {
    println("4xx response calling CollectionsTagsApi#assignPromptTags")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CollectionsTagsApi#assignPromptTags")
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

val apiInstance = CollectionsTagsApi()
val createCollectionRequest : CreateCollectionRequest =  // CreateCollectionRequest | 
try {
    apiInstance.createCollection(createCollectionRequest)
} catch (e: ClientException) {
    println("4xx response calling CollectionsTagsApi#createCollection")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CollectionsTagsApi#createCollection")
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

val apiInstance = CollectionsTagsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.deleteCollection(id, projectId)
} catch (e: ClientException) {
    println("4xx response calling CollectionsTagsApi#deleteCollection")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CollectionsTagsApi#deleteCollection")
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

<a id="listCollections"></a>
# **listCollections**
> listCollections(projectId, output)

List tags/collections

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CollectionsTagsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listCollections(projectId, output)
} catch (e: ClientException) {
    println("4xx response calling CollectionsTagsApi#listCollections")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CollectionsTagsApi#listCollections")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
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

<a id="listTags"></a>
# **listTags**
> listTags(projectId, output)

List tags (alias for /collections)

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CollectionsTagsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listTags(projectId, output)
} catch (e: ClientException) {
    println("4xx response calling CollectionsTagsApi#listTags")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CollectionsTagsApi#listTags")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
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

val apiInstance = CollectionsTagsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val updateCollectionRequest : UpdateCollectionRequest =  // UpdateCollectionRequest | 
try {
    apiInstance.updateCollection(id, updateCollectionRequest)
} catch (e: ClientException) {
    println("4xx response calling CollectionsTagsApi#updateCollection")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CollectionsTagsApi#updateCollection")
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

