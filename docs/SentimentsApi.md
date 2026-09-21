# SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listSentimentCategories**](SentimentsApi.md#listSentimentCategories) | **GET** /dimensions/sentiments | List sentiment categories |
| [**listSentimentRecords**](SentimentsApi.md#listSentimentRecords) | **GET** /sentiments | List sentiment records |


<a id="listSentimentCategories"></a>
# **listSentimentCategories**
> listSentimentCategories(projectId, output)

List sentiment categories

Sentiment metric keys + labels + colors. For records, use /sentiments.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SentimentsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listSentimentCategories(projectId, output)
} catch (e: ClientException) {
    println("4xx response calling SentimentsApi#listSentimentCategories")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SentimentsApi#listSentimentCategories")
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
val analysis : kotlin.String = analysis_example // kotlin.String | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
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
| **analysis** | **kotlin.String**| One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
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

