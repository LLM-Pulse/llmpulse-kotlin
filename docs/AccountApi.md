# AccountApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAccount**](AccountApi.md#getAccount) | **GET** /account | Account plan, quota usage and rate limits |


<a id="getAccount"></a>
# **getAccount**
> GetAccount200Response getAccount()

Account plan, quota usage and rate limits

Returns the account plan, tracking cadence, subscription window, how much of each quota is used (prompts, projects, competitors per project, monthly GEO Writer tasks, team members) and the published API rate limits. Limits resolve through the account owner, so a team member sees the capacity that applies to them. An unlimited quota returns limit and remaining as null with unlimited set to true, since Infinity is not representable in JSON. The subscription block is only present for callers who can access Billing and Plans in the app (the account owner, or a team member with billing access); everyone else gets the same response without that key. requests_per_minute is the ceiling of the key used for the call, not a fixed number.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AccountApi()
try {
    val result : GetAccount200Response = apiInstance.getAccount()
    println(result)
} catch (e: ClientException) {
    println("4xx response calling AccountApi#getAccount")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AccountApi#getAccount")
    e.printStackTrace()
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**GetAccount200Response**](GetAccount200Response.md)

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

