# StoreIntegrationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**acceptCatalogPromptSuggestions**](StoreIntegrationsApi.md#acceptCatalogPromptSuggestions) | **POST** /catalog_prompt_suggestions/accept | Accept catalog prompt suggestions |
| [**createCatalogPromptSuggestions**](StoreIntegrationsApi.md#createCatalogPromptSuggestions) | **POST** /catalog_prompt_suggestions | Suggest buyer prompts from catalog products |
| [**getStoreConnection**](StoreIntegrationsApi.md#getStoreConnection) | **GET** /store_connection | Match a store to a project |
| [**listAiOrders**](StoreIntegrationsApi.md#listAiOrders) | **GET** /ai_orders | Read AI-referred store orders |
| [**listCatalogPromptSuggestions**](StoreIntegrationsApi.md#listCatalogPromptSuggestions) | **GET** /catalog_prompt_suggestions | List catalog prompt suggestions |
| [**rejectCatalogPromptSuggestions**](StoreIntegrationsApi.md#rejectCatalogPromptSuggestions) | **POST** /catalog_prompt_suggestions/reject | Reject catalog prompt suggestions |
| [**replaceAiOrders**](StoreIntegrationsApi.md#replaceAiOrders) | **PUT** /ai_orders | Replace AI-referred store orders for a window |


<a id="acceptCatalogPromptSuggestions"></a>
# **acceptCatalogPromptSuggestions**
> CatalogPromptSuggestionsAcceptResponse acceptCatalogPromptSuggestions(catalogPromptSuggestionIdsRequest)

Accept catalog prompt suggestions

Starts tracking pending suggestions: each one becomes a prompt, tagged with a collection named after its product. Suggestions that are no longer pending come back in skipped. All accepted suggestions must share one country and language. When the new prompts would exceed the plan, the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = StoreIntegrationsApi()
val catalogPromptSuggestionIdsRequest : CatalogPromptSuggestionIdsRequest =  // CatalogPromptSuggestionIdsRequest | 
try {
    val result : CatalogPromptSuggestionsAcceptResponse = apiInstance.acceptCatalogPromptSuggestions(catalogPromptSuggestionIdsRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling StoreIntegrationsApi#acceptCatalogPromptSuggestions")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling StoreIntegrationsApi#acceptCatalogPromptSuggestions")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **catalogPromptSuggestionIdsRequest** | [**CatalogPromptSuggestionIdsRequest**](CatalogPromptSuggestionIdsRequest.md)|  | |

### Return type

[**CatalogPromptSuggestionsAcceptResponse**](CatalogPromptSuggestionsAcceptResponse.md)

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

<a id="createCatalogPromptSuggestions"></a>
# **createCatalogPromptSuggestions**
> CatalogPromptSuggestionsCreateResponse createCatalogPromptSuggestions(catalogPromptSuggestionsCreateRequest)

Suggest buyer prompts from catalog products

Writes buyer prompts for up to 20 catalog products and saves them as pending suggestions in the project&#39;s Suggested prompts queue, with the product recorded on each. Generation draws on the hourly prompt-suggestion allowance the app also uses (ERR_QUOTA_EXCEEDED once it is used up); a failed generation returns ERR_GENERATION_FAILED (502) and can be retried. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = StoreIntegrationsApi()
val catalogPromptSuggestionsCreateRequest : CatalogPromptSuggestionsCreateRequest =  // CatalogPromptSuggestionsCreateRequest | 
try {
    val result : CatalogPromptSuggestionsCreateResponse = apiInstance.createCatalogPromptSuggestions(catalogPromptSuggestionsCreateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling StoreIntegrationsApi#createCatalogPromptSuggestions")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling StoreIntegrationsApi#createCatalogPromptSuggestions")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **catalogPromptSuggestionsCreateRequest** | [**CatalogPromptSuggestionsCreateRequest**](CatalogPromptSuggestionsCreateRequest.md)|  | |

### Return type

[**CatalogPromptSuggestionsCreateResponse**](CatalogPromptSuggestionsCreateResponse.md)

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

<a id="getStoreConnection"></a>
# **getStoreConnection**
> StoreConnectionResponse getStoreConnection(platform, domain)

Match a store to a project

Tells a store app whether the API key&#39;s account can use it and which project the store belongs to: the live project whose domain equals the store domain, else one whose domain is a parent or a subdomain of it, else null. candidates lists every live project of the account so the app can offer a picker. Takes no project_id. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = StoreIntegrationsApi()
val platform : kotlin.String = platform_example // kotlin.String | Store platform
val domain : kotlin.String = domain_example // kotlin.String | Store domain, with or without scheme, e.g. acme-store.com
try {
    val result : StoreConnectionResponse = apiInstance.getStoreConnection(platform, domain)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling StoreIntegrationsApi#getStoreConnection")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling StoreIntegrationsApi#getStoreConnection")
    e.printStackTrace()
}
```

### Parameters
| **platform** | **kotlin.String**| Store platform | [enum: shopify] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **domain** | **kotlin.String**| Store domain, with or without scheme, e.g. acme-store.com | |

### Return type

[**StoreConnectionResponse**](StoreConnectionResponse.md)

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

<a id="listAiOrders"></a>
# **listAiOrders**
> AiOrdersResponse listAiOrders(projectId, platform, from, to)

Read AI-referred store orders

Reads back the AI-referred orders a store app pushed for a project: totals, one row per AI assistant and a daily series of the days with orders. Revenue values are decimal strings in currency. Team members need read access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = StoreIntegrationsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val platform : kotlin.String = platform_example // kotlin.String | Store platform
val from : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | First day (YYYY-MM-DD). Defaults to 89 days before to
val to : java.time.LocalDate = 2013-10-20 // java.time.LocalDate | Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days
try {
    val result : AiOrdersResponse = apiInstance.listAiOrders(projectId, platform, from, to)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling StoreIntegrationsApi#listAiOrders")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling StoreIntegrationsApi#listAiOrders")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **platform** | **kotlin.String**| Store platform | [optional] [default to Platform.shopify] [enum: shopify] |
| **from** | **java.time.LocalDate**| First day (YYYY-MM-DD). Defaults to 89 days before to | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **to** | **java.time.LocalDate**| Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days | [optional] |

### Return type

[**AiOrdersResponse**](AiOrdersResponse.md)

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

<a id="listCatalogPromptSuggestions"></a>
# **listCatalogPromptSuggestions**
> CatalogPromptSuggestionsResponse listCatalogPromptSuggestions(projectId, status, productExternalId, page, perPage)

List catalog prompt suggestions

Lists the buyer prompts suggested from a store catalog, oldest first, with their status and the product each one came from. Team members need read access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = StoreIntegrationsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val status : kotlin.String = status_example // kotlin.String | Only suggestions in this status
val productExternalId : kotlin.String = productExternalId_example // kotlin.String | Only suggestions for this store product id
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    val result : CatalogPromptSuggestionsResponse = apiInstance.listCatalogPromptSuggestions(projectId, status, productExternalId, page, perPage)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling StoreIntegrationsApi#listCatalogPromptSuggestions")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling StoreIntegrationsApi#listCatalogPromptSuggestions")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **status** | **kotlin.String**| Only suggestions in this status | [optional] [enum: pending, accepted, rejected] |
| **productExternalId** | **kotlin.String**| Only suggestions for this store product id | [optional] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**|  | [optional] [default to 50] |

### Return type

[**CatalogPromptSuggestionsResponse**](CatalogPromptSuggestionsResponse.md)

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

<a id="rejectCatalogPromptSuggestions"></a>
# **rejectCatalogPromptSuggestions**
> CatalogPromptSuggestionsRejectResponse rejectCatalogPromptSuggestions(catalogPromptSuggestionIdsRequest)

Reject catalog prompt suggestions

Marks pending suggestions as rejected; suggestions that are no longer pending stay as they are. Requires a &#x60;read_write&#x60; scope API key and, for team members, update access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = StoreIntegrationsApi()
val catalogPromptSuggestionIdsRequest : CatalogPromptSuggestionIdsRequest =  // CatalogPromptSuggestionIdsRequest | 
try {
    val result : CatalogPromptSuggestionsRejectResponse = apiInstance.rejectCatalogPromptSuggestions(catalogPromptSuggestionIdsRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling StoreIntegrationsApi#rejectCatalogPromptSuggestions")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling StoreIntegrationsApi#rejectCatalogPromptSuggestions")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **catalogPromptSuggestionIdsRequest** | [**CatalogPromptSuggestionIdsRequest**](CatalogPromptSuggestionIdsRequest.md)|  | |

### Return type

[**CatalogPromptSuggestionsRejectResponse**](CatalogPromptSuggestionsRejectResponse.md)

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

<a id="replaceAiOrders"></a>
# **replaceAiOrders**
> AiOrdersUpdateResponse replaceAiOrders(aiOrdersUpdateRequest)

Replace AI-referred store orders for a window

Replaces the daily AI-referred orders and revenue of the from..to window. Send the raw referring host or utm_source of each order&#39;s first visit as referrer: LLM Pulse classifies it and ignores anything that is not an AI assistant. Entries for the same day and assistant are summed. Every stored row of that project and platform inside the window is replaced, so pushing the same window again converges instead of counting twice. Rows are kept per project and platform, not per store, so one store reports per project. Requires a &#x60;read_write&#x60; scope API key and, for team members, update access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = StoreIntegrationsApi()
val aiOrdersUpdateRequest : AiOrdersUpdateRequest =  // AiOrdersUpdateRequest | 
try {
    val result : AiOrdersUpdateResponse = apiInstance.replaceAiOrders(aiOrdersUpdateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling StoreIntegrationsApi#replaceAiOrders")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling StoreIntegrationsApi#replaceAiOrders")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **aiOrdersUpdateRequest** | [**AiOrdersUpdateRequest**](AiOrdersUpdateRequest.md)|  | |

### Return type

[**AiOrdersUpdateResponse**](AiOrdersUpdateResponse.md)

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

