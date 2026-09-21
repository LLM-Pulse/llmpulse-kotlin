# SourcesCitationIntelligenceApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getCitedUrlContent**](SourcesCitationIntelligenceApi.md#getCitedUrlContent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**getCitedUrlDetail**](SourcesCitationIntelligenceApi.md#getCitedUrlDetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**getMentionsByCitingDomain**](SourcesCitationIntelligenceApi.md#getMentionsByCitingDomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**listCitationGroups**](SourcesCitationIntelligenceApi.md#listCitationGroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**listCitedUrlOccurrences**](SourcesCitationIntelligenceApi.md#listCitedUrlOccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |
| [**listSources**](SourcesCitationIntelligenceApi.md#listSources) | **GET** /dimensions/sources | List source URLs |


<a id="getCitedUrlContent"></a>
# **getCitedUrlContent**
> getCitedUrlContent(urlSha256, projectId)

Cited URL cached content

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null; content_gap_status is content_unavailable (or missing_page_cache). Mention arrays stay empty until usable content has completed analysis. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; mention counts are null when no URL has completed analysis.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SourcesCitationIntelligenceApi()
val urlSha256 : kotlin.String = urlSha256_example // kotlin.String | 64-character hex SHA-256 of the cited URL
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.getCitedUrlContent(urlSha256, projectId)
} catch (e: ClientException) {
    println("4xx response calling SourcesCitationIntelligenceApi#getCitedUrlContent")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SourcesCitationIntelligenceApi#getCitedUrlContent")
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

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null; content_gap_status is content_unavailable (or missing_page_cache). Mention arrays stay empty until usable content has completed analysis. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; mention counts are null when no URL has completed analysis.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SourcesCitationIntelligenceApi()
val urlSha256 : kotlin.String = urlSha256_example // kotlin.String | 64-character hex SHA-256 of the cited URL
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.getCitedUrlDetail(urlSha256, projectId)
} catch (e: ClientException) {
    println("4xx response calling SourcesCitationIntelligenceApi#getCitedUrlDetail")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SourcesCitationIntelligenceApi#getCitedUrlDetail")
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
> getMentionsByCitingDomain(projectId, domains, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to)

Mention share by citing domain

For the responses where each given source domain is cited, returns the share of those responses that mention the brand vs each competitor (brand + competitors sum to 100% per domain). Pass multiple domains to get the whole matrix in one call.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SourcesCitationIntelligenceApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val domains : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | Source domains to analyze, e.g. domains[]=gmac.com&domains[]=educaweb.com
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
try {
    apiInstance.getMentionsByCitingDomain(projectId, domains, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to)
} catch (e: ClientException) {
    println("4xx response calling SourcesCitationIntelligenceApi#getMentionsByCitingDomain")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SourcesCitationIntelligenceApi#getMentionsByCitingDomain")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **domains** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| Source domains to analyze, e.g. domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com | |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |

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

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position&#x3D;0. Owned and competitor source matching honor the project&#39;s exact-subdomain setting. Filter vocabulary aligns with &#x60;source_type&#x60; returned by the API. Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null; content_gap_status is content_unavailable (or missing_page_cache). Mention arrays stay empty until usable content has completed analysis. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; mention counts are null when no URL has completed analysis.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SourcesCitationIntelligenceApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val view : kotlin.String = view_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val order : kotlin.String = order_example // kotlin.String | 
val direction : kotlin.String = direction_example // kotlin.String | 
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val query : kotlin.String = query_example // kotlin.String | 
val sourceType : kotlin.String = sourceType_example // kotlin.String | 
val sentiment : kotlin.String = sentiment_example // kotlin.String | 
val contentGap : kotlin.String = contentGap_example // kotlin.String | 
try {
    apiInstance.listCitationGroups(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, from, to, query, sourceType, sentiment, contentGap)
} catch (e: ClientException) {
    println("4xx response calling SourcesCitationIntelligenceApi#listCitationGroups")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SourcesCitationIntelligenceApi#listCitationGroups")
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
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
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

val apiInstance = SourcesCitationIntelligenceApi()
val urlSha256 : kotlin.String = urlSha256_example // kotlin.String | 64-character hex SHA-256 of the cited URL
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    apiInstance.listCitedUrlOccurrences(urlSha256, projectId, page, perPage)
} catch (e: ClientException) {
    println("4xx response calling SourcesCitationIntelligenceApi#listCitedUrlOccurrences")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SourcesCitationIntelligenceApi#listCitedUrlOccurrences")
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

<a id="listSources"></a>
# **listSources**
> listSources(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, sourceType, mentionFilter, competitors, output)

List source URLs

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = SourcesCitationIntelligenceApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val sourceType : kotlin.String = sourceType_example // kotlin.String | Filter by source ownership. Owned and competitor matching honor the project's exact-subdomain setting.
val mentionFilter : kotlin.String = mentionFilter_example // kotlin.String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
val competitors : kotlin.String = competitors_example // kotlin.String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listSources(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, sourceType, mentionFilter, competitors, output)
} catch (e: ClientException) {
    println("4xx response calling SourcesCitationIntelligenceApi#listSources")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SourcesCitationIntelligenceApi#listSources")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **sourceType** | **kotlin.String**| Filter by source ownership. Owned and competitor matching honor the project&#39;s exact-subdomain setting. | [optional] [enum: owned, competitor, third_party] |
| **mentionFilter** | **kotlin.String**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] [enum: mentions_you, not_mentions_you, mentions_competitor, not_mentions_competitor, you_and_competitor, competitor_not_you, you_not_competitor, no_brands] |
| **competitors** | **kotlin.String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
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

