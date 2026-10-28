# APIKeysApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createApiKey**](APIKeysApi.md#createApiKey) | **POST** /api_keys | Create an API key limited to projects |
| [**listApiKeys**](APIKeysApi.md#listApiKeys) | **GET** /api_keys | List API keys |
| [**revokeApiKey**](APIKeysApi.md#revokeApiKey) | **DELETE** /api_keys/{id} | Revoke an API key |


<a id="createApiKey"></a>
# **createApiKey**
> CreateApiKey201Response createApiKey(createApiKeyRequest)

Create an API key limited to projects

Creates an API key limited to the projects in project_ids, owned by the same user as the calling key, and returns its secret token once: store it, since it cannot be read again. The key sees only those projects (any other project answers ERR_PROJECT_NOT_FOUND) and cannot act on the whole account, and the set of projects never changes. This endpoint never creates an account-wide key; create one in the app under API Keys. scope is read (default) or read_write. Every project must be one the caller can access: a project of another account, a deleted one or an unknown id answers ERR_PROJECT_NOT_FOUND and nothing is created. A user can hold up to 500 active keys; past that the request answers ERR_LIMIT_REACHED until a key is revoked. Requires an account-wide &#x60;read_write&#x60; scope API key on the Scale plan or above: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. A team member needs permission to create API keys and can only choose projects they can access.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = APIKeysApi()
val createApiKeyRequest : CreateApiKeyRequest =  // CreateApiKeyRequest | 
try {
    val result : CreateApiKey201Response = apiInstance.createApiKey(createApiKeyRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling APIKeysApi#createApiKey")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling APIKeysApi#createApiKey")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createApiKeyRequest** | [**CreateApiKeyRequest**](CreateApiKeyRequest.md)|  | |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)

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

<a id="listApiKeys"></a>
# **listApiKeys**
> ListApiKeys200Response listApiKeys(page, perPage)

List API keys

Lists the API keys of the user the calling key belongs to, newest first, revoked ones included: name, the visible prefix of the token, scope (read or read_write), the projects a key is limited to (project_scoped, project_ids; an empty list on an account-wide key), when it was created and last used, and when it was revoked. The secret token is only ever returned once, by POST /api_keys. Requires an account-wide &#x60;read_write&#x60; scope API key: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. Still answers after the account moves below the Scale plan, so old keys can be found and revoked. A team member needs the API Keys permission and sees only their own keys.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = APIKeysApi()
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | Default 20, max 100
try {
    val result : ListApiKeys200Response = apiInstance.listApiKeys(page, perPage)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling APIKeysApi#listApiKeys")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling APIKeysApi#listApiKeys")
    e.printStackTrace()
}
```

### Parameters
| **page** | **kotlin.Int**|  | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**| Default 20, max 100 | [optional] |

### Return type

[**ListApiKeys200Response**](ListApiKeys200Response.md)

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

<a id="revokeApiKey"></a>
# **revokeApiKey**
> RevokeApiKey200Response revokeApiKey(id)

Revoke an API key

Revokes an API key of the user the calling key belongs to: it stops working immediately and cannot be restored. Revoking a key that is already revoked answers the same way and keeps its original revocation time. A key of another user answers ERR_NOT_FOUND. The calling key can revoke itself. Requires an account-wide &#x60;read_write&#x60; scope API key: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. Still answers after the account moves below the Scale plan. A team member needs permission to delete API keys.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = APIKeysApi()
val id : kotlin.Int = 56 // kotlin.Int | The key id from GET /api_keys
try {
    val result : RevokeApiKey200Response = apiInstance.revokeApiKey(id)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling APIKeysApi#revokeApiKey")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling APIKeysApi#revokeApiKey")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int**| The key id from GET /api_keys | |

### Return type

[**RevokeApiKey200Response**](RevokeApiKey200Response.md)

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

