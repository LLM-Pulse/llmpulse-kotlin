# WebhooksApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createWebhook**](WebhooksApi.md#createWebhook) | **POST** /webhooks | Create a webhook subscription |
| [**deleteWebhook**](WebhooksApi.md#deleteWebhook) | **DELETE** /webhooks/{id} | Delete a webhook subscription |
| [**listWebhooks**](WebhooksApi.md#listWebhooks) | **GET** /webhooks | List webhook subscriptions |
| [**sampleWebhookPayloads**](WebhooksApi.md#sampleWebhookPayloads) | **GET** /webhooks/sample/{event_type} | Sample event payloads |


<a id="createWebhook"></a>
# **createWebhook**
> CreateWebhook201Response createWebhook(createWebhookRequest)

Create a webhook subscription

Subscribes a public HTTPS URL to a project event. LLM Pulse POSTs a JSON envelope (&#x60;event&#x60;, &#x60;occurred_at&#x60;, &#x60;project_id&#x60;, &#x60;subscription_id&#x60;, &#x60;data&#x60;) to the URL every time the event occurs, signed via the &#x60;X-LLMPulse-Signature&#x60; header (HMAC-SHA256 of the raw body computed with the subscription secret). Failed deliveries are retried 5 times with backoff; subscriptions auto-disable after 20 consecutive failed deliveries. Idempotent for the same project + event + URL. Requires a &#x60;read_write&#x60; scope API key and the Scale plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = WebhooksApi()
val createWebhookRequest : CreateWebhookRequest =  // CreateWebhookRequest | 
try {
    val result : CreateWebhook201Response = apiInstance.createWebhook(createWebhookRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling WebhooksApi#createWebhook")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling WebhooksApi#createWebhook")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createWebhookRequest** | [**CreateWebhookRequest**](CreateWebhookRequest.md)|  | |

### Return type

[**CreateWebhook201Response**](CreateWebhook201Response.md)

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

<a id="deleteWebhook"></a>
# **deleteWebhook**
> DeleteWebhook200Response deleteWebhook(id)

Delete a webhook subscription

Deletes a webhook subscription; the target URL stops receiving events immediately. Requires a &#x60;read_write&#x60; scope API key and the Scale plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = WebhooksApi()
val id : kotlin.Int = 56 // kotlin.Int | 
try {
    val result : DeleteWebhook200Response = apiInstance.deleteWebhook(id)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling WebhooksApi#deleteWebhook")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling WebhooksApi#deleteWebhook")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int**|  | |

### Return type

[**DeleteWebhook200Response**](DeleteWebhook200Response.md)

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

<a id="listWebhooks"></a>
# **listWebhooks**
> ListWebhooks200Response listWebhooks(projectId, page, perPage)

List webhook subscriptions

Lists active webhook subscriptions for the account, optionally filtered by project. Requires the Scale plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = WebhooksApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Optional project filter
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | Max 100
try {
    val result : ListWebhooks200Response = apiInstance.listWebhooks(projectId, page, perPage)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling WebhooksApi#listWebhooks")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling WebhooksApi#listWebhooks")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Optional project filter | [optional] |
| **page** | **kotlin.Int**|  | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**| Max 100 | [optional] |

### Return type

[**ListWebhooks200Response**](ListWebhooks200Response.md)

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

<a id="sampleWebhookPayloads"></a>
# **sampleWebhookPayloads**
> SampleWebhookPayloads200Response sampleWebhookPayloads(eventType, projectId)

Sample event payloads

Returns up to 3 example event payloads for the event type, built from the project&#39;s most recent real data (or a static sample when the project has no data). Used by integration editors such as the Zapier sample loader. Requires the Scale plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = WebhooksApi()
val eventType : kotlin.String = eventType_example // kotlin.String | 
val projectId : kotlin.Int = 56 // kotlin.Int | 
try {
    val result : SampleWebhookPayloads200Response = apiInstance.sampleWebhookPayloads(eventType, projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling WebhooksApi#sampleWebhookPayloads")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling WebhooksApi#sampleWebhookPayloads")
    e.printStackTrace()
}
```

### Parameters
| **eventType** | **kotlin.String**|  | [enum: mention.created, competitor_mention.created, citation.created, prompt_execution.completed, sentiment.negative_detected, recommendation.completed, intelligence_task.completed] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**|  | |

### Return type

[**SampleWebhookPayloads200Response**](SampleWebhookPayloads200Response.md)

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

