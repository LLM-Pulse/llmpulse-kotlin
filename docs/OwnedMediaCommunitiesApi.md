# OwnedMediaCommunitiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listOwnedMedia**](OwnedMediaCommunitiesApi.md#listOwnedMedia) | **GET** /dimensions/owned_media | List owned-media citations |
| [**listRedditCitations**](OwnedMediaCommunitiesApi.md#listRedditCitations) | **GET** /dimensions/reddit | List cited Reddit content |


<a id="listOwnedMedia"></a>
# **listOwnedMedia**
> listOwnedMedia(projectId, provider, page, perPage, view, store, owned, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List owned-media citations

Which owned-media content AI answers cite, by platform. &#x60;provider&#x60; is required. Each row carries a &#x60;yours&#x60; flag so you can compare your own presence against everyone else cited on the same platform. view&#x3D;own_citations returns the raw citations of the connected profile only and stays empty until a profile is connected. For Reddit use /dimensions/reddit. Requires the Growth plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = OwnedMediaCommunitiesApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val provider : kotlin.String = provider_example // kotlin.String | The platform to report on
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val view : kotlin.String = view_example // kotlin.String | Row shape; the allowed set depends on provider
val store : kotlin.String = store_example // kotlin.String | provider=mobile_apps only
val owned : kotlin.Boolean = true // kotlin.Boolean | Return only rows belonging to the account's own connected profile
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : GetTimeseriesCollectionIdParameter =  // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listOwnedMedia(projectId, provider, page, perPage, view, store, owned, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)
} catch (e: ClientException) {
    println("4xx response calling OwnedMediaCommunitiesApi#listOwnedMedia")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling OwnedMediaCommunitiesApi#listOwnedMedia")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **provider** | **kotlin.String**| The platform to report on | [enum: youtube, instagram, facebook, tiktok, linkedin, mobile_apps] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **view** | **kotlin.String**| Row shape; the allowed set depends on provider | [optional] [enum: videos, channels, posts, profiles, own_citations, apps] |
| **store** | **kotlin.String**| provider&#x3D;mobile_apps only | [optional] [default to Store.google_play] [enum: google_play, app_store] |
| **owned** | **kotlin.Boolean**| Return only rows belonging to the account&#39;s own connected profile | [optional] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
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
 - **Accept**: application/json

<a id="listRedditCitations"></a>
# **listRedditCitations**
> listRedditCitations(projectId, page, perPage, view, subreddit, author, status, owned, brand, order, direction, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List cited Reddit content

Which Reddit content AI answers cite for your tracked prompts. view&#x3D;subreddits (default) returns one row per subreddit with its citation count, unique authors and positive/negative sentiment split; view&#x3D;authors returns one row per author; view&#x3D;threads returns the individual cited threads with upvotes, comments, average position and dominant sentiment. Requires the Growth plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = OwnedMediaCommunitiesApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val view : kotlin.String = view_example // kotlin.String | 
val subreddit : kotlin.String = subreddit_example // kotlin.String | Filter to one subreddit (name without the r/ prefix)
val author : kotlin.String = author_example // kotlin.String | Filter to one Reddit author
val status : kotlin.String = status_example // kotlin.String | view=threads only
val owned : kotlin.Boolean = true // kotlin.Boolean | Return only subreddits/authors the account has claimed as its own
val brand : kotlin.String = brand_example // kotlin.String | Filter to citations whose scraped Reddit content mentions a brand: 'brand' for the tracked brand, or a competitor id. Reads the page content, not the AI answer.
val order : kotlin.String = order_example // kotlin.String | Sort field; the allowed set depends on view
val direction : kotlin.String = direction_example // kotlin.String | 
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : GetTimeseriesCollectionIdParameter =  // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listRedditCitations(projectId, page, perPage, view, subreddit, author, status, owned, brand, order, direction, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)
} catch (e: ClientException) {
    println("4xx response calling OwnedMediaCommunitiesApi#listRedditCitations")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling OwnedMediaCommunitiesApi#listRedditCitations")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **view** | **kotlin.String**|  | [optional] [default to View.subreddits] [enum: subreddits, authors, threads] |
| **subreddit** | **kotlin.String**| Filter to one subreddit (name without the r/ prefix) | [optional] |
| **author** | **kotlin.String**| Filter to one Reddit author | [optional] |
| **status** | **kotlin.String**| view&#x3D;threads only | [optional] [enum: open, archived] |
| **owned** | **kotlin.Boolean**| Return only subreddits/authors the account has claimed as its own | [optional] |
| **brand** | **kotlin.String**| Filter to citations whose scraped Reddit content mentions a brand: &#39;brand&#39; for the tracked brand, or a competitor id. Reads the page content, not the AI answer. | [optional] |
| **order** | **kotlin.String**| Sort field; the allowed set depends on view | [optional] [enum: citations, subreddit, unique_authors, positive_pct, negative_pct, author, avg_position, upvotes, comments, sentiment] |
| **direction** | **kotlin.String**|  | [optional] [default to Direction.desc] [enum: asc, desc] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
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
 - **Accept**: application/json

