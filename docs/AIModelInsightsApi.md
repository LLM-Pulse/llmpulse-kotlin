# AIModelInsightsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAiModelInsightsSummary**](AIModelInsightsApi.md#getAiModelInsightsSummary) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary |
| [**getAiModelPositionDistribution**](AIModelInsightsApi.md#getAiModelPositionDistribution) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison |
| [**getAiOverviewResults**](AIModelInsightsApi.md#getAiOverviewResults) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability |


<a id="getAiModelInsightsSummary"></a>
# **getAiModelInsightsSummary**
> getAiModelInsightsSummary(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, competitors)

AI Model Insights summary

Per-model mentions, citations, brand net sentiment with raw counts, weighted visibility totals/shares, plus actor matrices. All actor entries use the standard shape &#x60;{ type, id, competitor_id, name, domain }&#x60; with bare (scheme-less) domains.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AIModelInsightsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val granularity : kotlin.String = granularity_example // kotlin.String | 
val collectionId : GetTimeseriesCollectionIdParameter =  // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val competitors : kotlin.String = competitors_example // kotlin.String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
try {
    apiInstance.getAiModelInsightsSummary(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, competitors)
} catch (e: ClientException) {
    println("4xx response calling AIModelInsightsApi#getAiModelInsightsSummary")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AIModelInsightsApi#getAiModelInsightsSummary")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **competitors** | **kotlin.String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |

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

<a id="getAiModelPositionDistribution"></a>
# **getAiModelPositionDistribution**
> getAiModelPositionDistribution(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, model, brand1, brand2)

Position distribution comparison

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AIModelInsightsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val granularity : kotlin.String = granularity_example // kotlin.String | 
val collectionId : GetTimeseriesCollectionIdParameter =  // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val brand1 : kotlin.Int = 56 // kotlin.Int | Competitor ID for the first comparison brand (omit to compare project brand)
val brand2 : kotlin.Int = 56 // kotlin.Int | 
try {
    apiInstance.getAiModelPositionDistribution(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, model, brand1, brand2)
} catch (e: ClientException) {
    println("4xx response calling AIModelInsightsApi#getAiModelPositionDistribution")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AIModelInsightsApi#getAiModelPositionDistribution")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **brand1** | **kotlin.Int**| Competitor ID for the first comparison brand (omit to compare project brand) | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **brand2** | **kotlin.Int**|  | [optional] |

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

<a id="getAiOverviewResults"></a>
# **getAiOverviewResults**
> getAiOverviewResults(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, page, perPage)

Google AI Overview result availability

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AIModelInsightsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val granularity : kotlin.String = granularity_example // kotlin.String | 
val collectionId : GetTimeseriesCollectionIdParameter =  // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    apiInstance.getAiOverviewResults(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, page, perPage)
} catch (e: ClientException) {
    println("4xx response calling AIModelInsightsApi#getAiOverviewResults")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AIModelInsightsApi#getAiOverviewResults")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
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
 - **Accept**: Not defined

