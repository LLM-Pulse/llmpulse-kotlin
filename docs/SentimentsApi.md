# SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listSentimentRecords**](SentimentsApi.md#listSentimentRecords) | **GET** /sentiments | List sentiment records |


<a id="listSentimentRecords"></a>
# **listSentimentRecords**
> listSentimentRecords(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage)

List sentiment records

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SentimentsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val competitorId : kotlin.Int = 56 // kotlin.Int | 
val brandOnly : kotlin.Boolean = true // kotlin.Boolean | 
val analysis : kotlin.String = analysis_example // kotlin.String | 
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.Int = 56 // kotlin.Int | 
val countryCode : kotlin.String = countryCode_example // kotlin.String | ISO country code (e.g. US, GB, DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | ISO language code (e.g. en, es, de)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    apiInstance.listSentimentRecords(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage)
} catch (e: ClientException) {
    println("4xx response calling SentimentsApi#listSentimentRecords")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SentimentsApi#listSentimentRecords")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **competitorId** | **kotlin.Int**|  | [optional] |
| **brandOnly** | **kotlin.Boolean**|  | [optional] |
| **analysis** | **kotlin.String**|  | [optional] [enum: very_positive, positive, neutral, negative, very_negative] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **kotlin.Int**|  | [optional] |
| **countryCode** | **kotlin.String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **kotlin.String**| ISO language code (e.g. en, es, de) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**|  | [optional] |
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

