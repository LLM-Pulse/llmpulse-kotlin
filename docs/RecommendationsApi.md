# RecommendationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getRecommendation**](RecommendationsApi.md#getRecommendation) | **GET** /recommendations/{id} | Get recommendation run with items |
| [**launchRecommendations**](RecommendationsApi.md#launchRecommendations) | **POST** /recommendations | Launch a recommendations generation |
| [**listRecommendations**](RecommendationsApi.md#listRecommendations) | **GET** /recommendations | List recommendation runs |
| [**updateRecommendationItem**](RecommendationsApi.md#updateRecommendationItem) | **PATCH** /recommendations/{id}/items/{item_id} | Complete, archive or restore a recommendation item |


<a id="getRecommendation"></a>
# **getRecommendation**
> getRecommendation(id, projectId, itemStatus, resolveSourceRefs)

Get recommendation run with items

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = RecommendationsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val itemStatus : kotlin.String = itemStatus_example // kotlin.String | 
val resolveSourceRefs : kotlin.Boolean = true // kotlin.Boolean | 
try {
    apiInstance.getRecommendation(id, projectId, itemStatus, resolveSourceRefs)
} catch (e: ClientException) {
    println("4xx response calling RecommendationsApi#getRecommendation")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling RecommendationsApi#getRecommendation")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| **projectId** | **kotlin.Int**| Project ID | |
| **itemStatus** | **kotlin.String**|  | [optional] [enum: active, completed, archived] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **resolveSourceRefs** | **kotlin.Boolean**|  | [optional] [default to true] |

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

<a id="launchRecommendations"></a>
# **launchRecommendations**
> launchRecommendations(launchRecommendationsRequest)

Launch a recommendations generation

Launches a full-scope recommendations generation (async job, 1-3 minutes; poll GET /recommendations/{id} until status is completed). Consumes the project weekly recommendation-item budget: returns ERR_LIMIT_REACHED when it is exhausted or when a generation of the same type is already pending/processing. sentiment_reputation requires the Scale plan or above. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = RecommendationsApi()
val launchRecommendationsRequest : LaunchRecommendationsRequest =  // LaunchRecommendationsRequest | 
try {
    apiInstance.launchRecommendations(launchRecommendationsRequest)
} catch (e: ClientException) {
    println("4xx response calling RecommendationsApi#launchRecommendations")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling RecommendationsApi#launchRecommendations")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **launchRecommendationsRequest** | [**LaunchRecommendationsRequest**](LaunchRecommendationsRequest.md)|  | |

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

<a id="listRecommendations"></a>
# **listRecommendations**
> RecommendationsResponse listRecommendations(projectId, recommendationType, status, page, perPage)

List recommendation runs

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = RecommendationsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val recommendationType : kotlin.String = recommendationType_example // kotlin.String | 
val status : kotlin.String = status_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    val result : RecommendationsResponse = apiInstance.listRecommendations(projectId, recommendationType, status, page, perPage)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling RecommendationsApi#listRecommendations")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling RecommendationsApi#listRecommendations")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **recommendationType** | **kotlin.String**|  | [optional] [enum: ai_visibility, social_community, brand_building, sentiment_reputation] |
| **status** | **kotlin.String**|  | [optional] [enum: pending, processing, completed, failed] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |

### Return type

[**RecommendationsResponse**](RecommendationsResponse.md)

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

<a id="updateRecommendationItem"></a>
# **updateRecommendationItem**
> RecommendationItemUpdateResponse updateRecommendationItem(id, itemId, updateRecommendationItemRequest)

Complete, archive or restore a recommendation item

Moves one item of a recommendation run between &#x60;active&#x60;, &#x60;completed&#x60; and &#x60;archived&#x60;, exactly like the complete, archive and restore buttons on the Recommendations page, and stamps &#x60;status_changed_at&#x60;. Returns the item in the shape &#x60;GET /recommendations/{id}&#x60; lists items. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on Recommendations (the permission the page uses for these buttons).

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = RecommendationsApi()
val id : kotlin.Int = 56 // kotlin.Int | Recommendation run id
val itemId : kotlin.Int = 56 // kotlin.Int | Item id, from the items of GET /recommendations/{id}
val updateRecommendationItemRequest : UpdateRecommendationItemRequest =  // UpdateRecommendationItemRequest | 
try {
    val result : RecommendationItemUpdateResponse = apiInstance.updateRecommendationItem(id, itemId, updateRecommendationItemRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling RecommendationsApi#updateRecommendationItem")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling RecommendationsApi#updateRecommendationItem")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**| Recommendation run id | |
| **itemId** | **kotlin.Int**| Item id, from the items of GET /recommendations/{id} | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updateRecommendationItemRequest** | [**UpdateRecommendationItemRequest**](UpdateRecommendationItemRequest.md)|  | |

### Return type

[**RecommendationItemUpdateResponse**](RecommendationItemUpdateResponse.md)

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

