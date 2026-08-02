# AnswersApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAnswer**](AnswersApi.md#getAnswer) | **GET** /answers/{id} | Get one AI response |
| [**listAnswers**](AnswersApi.md#listAnswers) | **GET** /answers | List AI responses |


<a id="getAnswer"></a>
# **getAnswer**
> AnswerDetails getAnswer(id, projectId, includeSourcePageDetails)

Get one AI response

Full answer with mentions, citations, sentiments, sources, shopping_products, brand_entities, fan_out_queries. Pass &#x60;include_source_page_details&#x3D;true&#x60; to nest page-cache metadata under each source.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AnswersApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val includeSourcePageDetails : kotlin.Boolean = true // kotlin.Boolean | 
try {
    val result : AnswerDetails = apiInstance.getAnswer(id, projectId, includeSourcePageDetails)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling AnswersApi#getAnswer")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AnswersApi#getAnswer")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| **projectId** | **kotlin.Int**| Project ID | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **includeSourcePageDetails** | **kotlin.Boolean**|  | [optional] [default to false] |

### Return type

[**AnswerDetails**](AnswerDetails.md)

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

<a id="listAnswers"></a>
# **listAnswers**
> listAnswers(projectId, model, collectionId, countryCode, languageCode, prompt, mentionFilter, citationFilter, competitors, from, to, page, perPage, query)

List AI responses

Successful prompt-execution responses with truncated content (max 10,000 chars). Pass &#x60;query&#x60; for case-insensitive full-text search inside response texts: &#x60;total&#x60; becomes the exact count of matching responses and each item returns &#x60;snippet&#x60; + &#x60;match_count&#x60; instead of &#x60;response&#x60;/&#x60;response_truncated&#x60;.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AnswersApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.Int = 56 // kotlin.Int | 
val countryCode : kotlin.String = countryCode_example // kotlin.String | ISO country code (e.g. US, GB, DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | ISO language code (e.g. en, es, de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val mentionFilter : kotlin.String = mentionFilter_example // kotlin.String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
val citationFilter : kotlin.String = citationFilter_example // kotlin.String | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
val competitors : kotlin.String = competitors_example // kotlin.String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val query : kotlin.String = query_example // kotlin.String | Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode.
try {
    apiInstance.listAnswers(projectId, model, collectionId, countryCode, languageCode, prompt, mentionFilter, citationFilter, competitors, from, to, page, perPage, query)
} catch (e: ClientException) {
    println("4xx response calling AnswersApi#listAnswers")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AnswersApi#listAnswers")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **kotlin.Int**|  | [optional] |
| **countryCode** | **kotlin.String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **kotlin.String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **mentionFilter** | **kotlin.String**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] [enum: mentions_you, not_mentions_you, mentions_competitor, not_mentions_competitor, you_and_competitor, competitor_not_you, you_not_competitor, no_brands] |
| **citationFilter** | **kotlin.String**| Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional] [enum: cites_you, not_cites_you, cites_competitor, not_cites_competitor, you_and_competitor, competitor_not_you, you_not_competitor, cites_no_brands] |
| **competitors** | **kotlin.String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**|  | [optional] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **query** | **kotlin.String**| Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode. | [optional] |

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

