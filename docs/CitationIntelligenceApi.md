# CitationIntelligenceApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getCitedUrlContent**](CitationIntelligenceApi.md#getCitedUrlContent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**getCitedUrlDetail**](CitationIntelligenceApi.md#getCitedUrlDetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**getMentionsByCitingDomain**](CitationIntelligenceApi.md#getMentionsByCitingDomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**listCitationGroups**](CitationIntelligenceApi.md#listCitationGroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**listCitedUrlOccurrences**](CitationIntelligenceApi.md#listCitedUrlOccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |


<a id="getCitedUrlContent"></a>
# **getCitedUrlContent**
> getCitedUrlContent(urlSha256, projectId)

Cited URL cached content

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CitationIntelligenceApi()
val urlSha256 : kotlin.String = urlSha256_example // kotlin.String | 64-character hex SHA-256 of the cited URL
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.getCitedUrlContent(urlSha256, projectId)
} catch (e: ClientException) {
    println("4xx response calling CitationIntelligenceApi#getCitedUrlContent")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CitationIntelligenceApi#getCitedUrlContent")
    e.printStackTrace()
}
```

### Parameters
| **urlSha256** | **kotlin.String**| 64-character hex SHA-256 of the cited URL | |
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

<a id="getCitedUrlDetail"></a>
# **getCitedUrlDetail**
> getCitedUrlDetail(urlSha256, projectId)

Cited URL detail

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CitationIntelligenceApi()
val urlSha256 : kotlin.String = urlSha256_example // kotlin.String | 64-character hex SHA-256 of the cited URL
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.getCitedUrlDetail(urlSha256, projectId)
} catch (e: ClientException) {
    println("4xx response calling CitationIntelligenceApi#getCitedUrlDetail")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CitationIntelligenceApi#getCitedUrlDetail")
    e.printStackTrace()
}
```

### Parameters
| **urlSha256** | **kotlin.String**| 64-character hex SHA-256 of the cited URL | |
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

<a id="getMentionsByCitingDomain"></a>
# **getMentionsByCitingDomain**
> getMentionsByCitingDomain(projectId, domains, model, collectionId, countryCode, languageCode, prompt, from, to)

Mention share by citing domain

For the responses where each given source domain is cited, returns the share of those responses that mention the brand vs each competitor (brand + competitors sum to 100% per domain). Pass multiple domains to get the whole matrix in one call.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CitationIntelligenceApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val domains : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | Source domains to analyze, e.g. domains[]=gmac.com&domains[]=educaweb.com
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.Int = 56 // kotlin.Int | 
val countryCode : kotlin.String = countryCode_example // kotlin.String | ISO country code (e.g. US, GB, DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | ISO language code (e.g. en, es, de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
try {
    apiInstance.getMentionsByCitingDomain(projectId, domains, model, collectionId, countryCode, languageCode, prompt, from, to)
} catch (e: ClientException) {
    println("4xx response calling CitationIntelligenceApi#getMentionsByCitingDomain")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CitationIntelligenceApi#getMentionsByCitingDomain")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **domains** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| Source domains to analyze, e.g. domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com | |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **kotlin.Int**|  | [optional] |
| **countryCode** | **kotlin.String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **kotlin.String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **to** | **java.time.OffsetDateTime**|  | [optional] |

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

<a id="listCitationGroups"></a>
# **listCitationGroups**
> listCitationGroups(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, from, to, query, sourceType, sentiment, contentGap)

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position&#x3D;0. Owned and competitor source matching honor the project&#39;s exact-subdomain setting. Filter vocabulary aligns with &#x60;source_type&#x60; returned by the API.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CitationIntelligenceApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val view : kotlin.String = view_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val order : kotlin.String = order_example // kotlin.String | 
val direction : kotlin.String = direction_example // kotlin.String | 
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.Int = 56 // kotlin.Int | 
val countryCode : kotlin.String = countryCode_example // kotlin.String | ISO country code (e.g. US, GB, DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | ISO language code (e.g. en, es, de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val query : kotlin.String = query_example // kotlin.String | 
val sourceType : kotlin.String = sourceType_example // kotlin.String | 
val sentiment : kotlin.String = sentiment_example // kotlin.String | 
val contentGap : kotlin.String = contentGap_example // kotlin.String | 
try {
    apiInstance.listCitationGroups(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, from, to, query, sourceType, sentiment, contentGap)
} catch (e: ClientException) {
    println("4xx response calling CitationIntelligenceApi#listCitationGroups")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CitationIntelligenceApi#listCitationGroups")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **view** | **kotlin.String**|  | [optional] [default to View.url] [enum: url, domain, host] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **order** | **kotlin.String**|  | [optional] [enum: group_key, total_responses, total_citations, citation_rate, avg_citation_position, first_seen_at, last_seen_at] |
| **direction** | **kotlin.String**|  | [optional] [enum: asc, desc] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **kotlin.Int**|  | [optional] |
| **countryCode** | **kotlin.String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **kotlin.String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**|  | [optional] |
| **query** | **kotlin.String**|  | [optional] |
| **sourceType** | **kotlin.String**|  | [optional] [enum: owned, competitor, third_party, social_media, own_domain, ugc, background] |
| **sentiment** | **kotlin.String**|  | [optional] [enum: negative] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **contentGap** | **kotlin.String**|  | [optional] [enum: mentioned, gap] |

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

<a id="listCitedUrlOccurrences"></a>
# **listCitedUrlOccurrences**
> listCitedUrlOccurrences(urlSha256, projectId, page, perPage)

Cited URL occurrences

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CitationIntelligenceApi()
val urlSha256 : kotlin.String = urlSha256_example // kotlin.String | 64-character hex SHA-256 of the cited URL
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    apiInstance.listCitedUrlOccurrences(urlSha256, projectId, page, perPage)
} catch (e: ClientException) {
    println("4xx response calling CitationIntelligenceApi#listCitedUrlOccurrences")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CitationIntelligenceApi#listCitedUrlOccurrences")
    e.printStackTrace()
}
```

### Parameters
| **urlSha256** | **kotlin.String**| 64-character hex SHA-256 of the cited URL | |
| **projectId** | **kotlin.Int**| Project ID | |
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

