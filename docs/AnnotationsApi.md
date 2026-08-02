# AnnotationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAnnotation**](AnnotationsApi.md#createAnnotation) | **POST** /annotations | Create a timeline annotation |
| [**deleteAnnotation**](AnnotationsApi.md#deleteAnnotation) | **DELETE** /annotations/{id} | Delete a timeline annotation |
| [**listAnnotations**](AnnotationsApi.md#listAnnotations) | **GET** /annotations | List timeline annotations |
| [**updateAnnotation**](AnnotationsApi.md#updateAnnotation) | **PATCH** /annotations/{id} | Update a timeline annotation |


<a id="createAnnotation"></a>
# **createAnnotation**
> createAnnotation(createAnnotationRequest)

Create a timeline annotation

Marks a date in the project timeseries with a title + description. Requires the **Growth** plan or above. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AnnotationsApi()
val createAnnotationRequest : CreateAnnotationRequest =  // CreateAnnotationRequest | 
try {
    apiInstance.createAnnotation(createAnnotationRequest)
} catch (e: ClientException) {
    println("4xx response calling AnnotationsApi#createAnnotation")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AnnotationsApi#createAnnotation")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createAnnotationRequest** | [**CreateAnnotationRequest**](CreateAnnotationRequest.md)|  | |

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

<a id="deleteAnnotation"></a>
# **deleteAnnotation**
> deleteAnnotation(id, projectId)

Delete a timeline annotation

Deletes an annotation. Same ownership rule as PATCH. Requires the **Growth** plan or above and a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AnnotationsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.deleteAnnotation(id, projectId)
} catch (e: ClientException) {
    println("4xx response calling AnnotationsApi#deleteAnnotation")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AnnotationsApi#deleteAnnotation")
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

<a id="listAnnotations"></a>
# **listAnnotations**
> listAnnotations(projectId, from, to, annotationCategoryId, page, perPage)

List timeline annotations

Lists the project timeline annotations (user-created + system), newest first. The category field tells them apart; editable says whether the requesting user may modify the row. Requires the **Growth** plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AnnotationsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | 
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | 
val annotationCategoryId : kotlin.Int = 56 // kotlin.Int | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    apiInstance.listAnnotations(projectId, from, to, annotationCategoryId, page, perPage)
} catch (e: ClientException) {
    println("4xx response calling AnnotationsApi#listAnnotations")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AnnotationsApi#listAnnotations")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **from** | **java.time.LocalDate**|  | [optional] |
| **to** | **java.time.LocalDate**|  | [optional] |
| **annotationCategoryId** | **kotlin.Int**|  | [optional] |
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

<a id="updateAnnotation"></a>
# **updateAnnotation**
> updateAnnotation(id, updateAnnotationRequest)

Update a timeline annotation

Updates title, description, annotation_date, color and/or annotation_category_id. Only user-created annotations belonging to the requesting user can be updated (system annotations never). Requires the **Growth** plan or above and a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AnnotationsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val updateAnnotationRequest : UpdateAnnotationRequest =  // UpdateAnnotationRequest | 
try {
    apiInstance.updateAnnotation(id, updateAnnotationRequest)
} catch (e: ClientException) {
    println("4xx response calling AnnotationsApi#updateAnnotation")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AnnotationsApi#updateAnnotation")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updateAnnotationRequest** | [**UpdateAnnotationRequest**](UpdateAnnotationRequest.md)|  | |

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

