# CompetitorsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCompetitor**](CompetitorsApi.md#createCompetitor) | **POST** /competitors | Add a competitor |
| [**deleteCompetitor**](CompetitorsApi.md#deleteCompetitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**updateCompetitor**](CompetitorsApi.md#updateCompetitor) | **PATCH** /competitors/{id} | Update a competitor |


<a id="createCompetitor"></a>
# **createCompetitor**
> createCompetitor(createCompetitorRequest)

Add a competitor

Adds a competitor (brand name + domain) to a project. Honours the per-plan max competitors cap. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CompetitorsApi()
val createCompetitorRequest : CreateCompetitorRequest =  // CreateCompetitorRequest | 
try {
    apiInstance.createCompetitor(createCompetitorRequest)
} catch (e: ClientException) {
    println("4xx response calling CompetitorsApi#createCompetitor")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CompetitorsApi#createCompetitor")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createCompetitorRequest** | [**CreateCompetitorRequest**](CreateCompetitorRequest.md)|  | |

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

<a id="deleteCompetitor"></a>
# **deleteCompetitor**
> deleteCompetitor(id, projectId)

Delete a competitor

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; its tracked data is purged by a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CompetitorsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.deleteCompetitor(id, projectId)
} catch (e: ClientException) {
    println("4xx response calling CompetitorsApi#deleteCompetitor")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CompetitorsApi#deleteCompetitor")
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

<a id="updateCompetitor"></a>
# **updateCompetitor**
> updateCompetitor(id, updateCompetitorRequest)

Update a competitor

Updates brand_name, matching_names (full replacement list; the brand name is always included automatically) and/or color. The domain is immutable after creation. Name changes re-run mention/citation matching in the background: the competitor shows processing&#x3D;true for a few minutes and further edits are rejected meanwhile. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CompetitorsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val updateCompetitorRequest : UpdateCompetitorRequest =  // UpdateCompetitorRequest | 
try {
    apiInstance.updateCompetitor(id, updateCompetitorRequest)
} catch (e: ClientException) {
    println("4xx response calling CompetitorsApi#updateCompetitor")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CompetitorsApi#updateCompetitor")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updateCompetitorRequest** | [**UpdateCompetitorRequest**](UpdateCompetitorRequest.md)|  | |

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

