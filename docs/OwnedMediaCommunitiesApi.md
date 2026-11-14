# OwnedMediaCommunitiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getOwnedMediaProfiles**](OwnedMediaCommunitiesApi.md#getOwnedMediaProfiles) | **GET** /projects/{id}/owned_media | Get a project&#39;s owned-media profiles |
| [**getOwnedMediaSummary**](OwnedMediaCommunitiesApi.md#getOwnedMediaSummary) | **GET** /dimensions/owned_media/summary | Get an owned-media summary |
| [**listOwnedMedia**](OwnedMediaCommunitiesApi.md#listOwnedMedia) | **GET** /dimensions/owned_media | List owned-media citations |
| [**listOwnedMediaCitingPrompts**](OwnedMediaCommunitiesApi.md#listOwnedMediaCitingPrompts) | **GET** /dimensions/owned_media/citing_prompts | List the answers citing an owned-media item |
| [**listRedditCitations**](OwnedMediaCommunitiesApi.md#listRedditCitations) | **GET** /dimensions/reddit | List cited Reddit content |
| [**updateOwnedMediaProfiles**](OwnedMediaCommunitiesApi.md#updateOwnedMediaProfiles) | **PATCH** /projects/{id}/owned_media | Update a project&#39;s owned-media profiles |


<a id="getOwnedMediaProfiles"></a>
# **getOwnedMediaProfiles**
> OwnedMediaProfilesResponse getOwnedMediaProfiles(id)

Get a project&#39;s owned-media profiles

The profiles whose citations count as yours in the Owned Media and YouTube Intelligence reports, as Project Settings &gt; Brand channels shows them. platforms holds one entry per platform with whether it is connected, how many extra profiles it accepts and its profiles: the main one, the extra ones, and on Reddit the claimed subreddits and usernames, each with its URL, handle, store (for apps), name, avatar and the state of the scrape that reads them. settings holds the current value of every field PATCH accepts, ready to edit and send back. Requires the Growth plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = OwnedMediaCommunitiesApi()
val id : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    val result : OwnedMediaProfilesResponse = apiInstance.getOwnedMediaProfiles(id)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling OwnedMediaCommunitiesApi#getOwnedMediaProfiles")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling OwnedMediaCommunitiesApi#getOwnedMediaProfiles")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int**| Project ID | |

### Return type

[**OwnedMediaProfilesResponse**](OwnedMediaProfilesResponse.md)

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

<a id="getOwnedMediaSummary"></a>
# **getOwnedMediaSummary**
> OwnedMediaSummaryResponse getOwnedMediaSummary(projectId, provider, model, collectionId, countryCode, languageCode, brandKind, range, from, to)

Get an owned-media summary

The numbers behind one Owned Media tab. kpis gives platform citations (total), yours (the account&#39;s own profiles and content), your_profile and your_content separately where available, and share_pct; previous gives the same KPIs for the period of the same length that ends just before from, and changes gives the difference (percent for counts, percentage points for share_pct and positive_pct, null when there is nothing to compare). weekly remains the Monday-anchored series. Every provider returns activity by actual project reporting period, with date at the period start, citations, yours and other; yours and other are null for provider&#x3D;overview. The overview also includes each readable platform&#39;s activity under platforms, with date and citations. Periods without runs are omitted, and a period with runs but no citation has zero. Activity counts use the selected date window. by_model and by_country split citations; content_types (reel, post, tv, pulse, or regular, shorts and live on YouTube) and age_buckets cover posts and videos. provider&#x3D;mobile_apps adds stores and per-store totals; provider&#x3D;trustpilot counts trustpilot.com citations, yours being those of the profile of the account&#39;s own domains, and adds replies: how the brand answers the reviews LLM Pulse holds for its own domain&#39;s profile (reviews_held, replied_count, not_replied_count, reply_rate_pct, median_reply_hours), whatever the date window; provider&#x3D;overview returns one rollup per readable platform. provider&#x3D;reddit adds unique_subreddits, unique_authors, positive_pct, and positive, neutral and negative sentiment counts in activity for the citing AI answers, plus subreddit_activity for the top five subreddits and Others, positions and brand_share. A team member also needs the YouTube Intelligence permission for provider&#x3D;youtube or Reddit Intelligence for provider&#x3D;reddit. Defaults to the last 30 days. Requires the Growth plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = OwnedMediaCommunitiesApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val provider : kotlin.String = provider_example // kotlin.String | The platform to summarize, or overview for every platform at once
val model : kotlin.String = model_example // kotlin.String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
try {
    val result : OwnedMediaSummaryResponse = apiInstance.getOwnedMediaSummary(projectId, provider, model, collectionId, countryCode, languageCode, brandKind, range, from, to)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling OwnedMediaCommunitiesApi#getOwnedMediaSummary")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling OwnedMediaCommunitiesApi#getOwnedMediaSummary")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **provider** | **kotlin.String**| The platform to summarize, or overview for every platform at once | [enum: youtube, instagram, facebook, tiktok, linkedin, mobile_apps, reddit, trustpilot, overview] |
| **model** | **kotlin.String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |
| **from** | **java.time.OffsetDateTime**| Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |

### Return type

[**OwnedMediaSummaryResponse**](OwnedMediaSummaryResponse.md)

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

<a id="listOwnedMedia"></a>
# **listOwnedMedia**
> OwnedMediaListResponse listOwnedMedia(projectId, provider, page, perPage, view, store, owned, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List owned-media citations

Which owned-media content AI answers cite, by platform. &#x60;provider&#x60; is required. Each row carries a &#x60;yours&#x60; flag so you can compare your own presence against everyone else cited on the same platform. Video, post, channel and profile rows also carry their image (thumbnail_url or avatar_url, our cached copy where one exists), their average position in the answers and, on YouTube, the video id, the channel handle and URL, and the channel key that /dimensions/owned_media/citing_prompts accepts. &#x60;view&#x3D;activity&#x60; returns one row per entity and actual reporting period; periods without runs are omitted, while a run without a citation has a real zero. Its citation counts cover the selected date window; profile, channel and app metadata are current values, not historical growth. For provider&#x3D;mobile_apps, select the store with &#x60;store&#x60;. For provider&#x3D;trustpilot, &#x60;view&#x3D;profiles&#x60; (the default) lists the cited Trustpilot profiles with their rating and review count, &#x60;view&#x3D;brands&#x60; the brand and each competitor with their profile&#39;s rating, its change since the previous monthly read, review count, read status and citations, plus how the business answers its reviews (reviews_held, replied_count, not_replied_count, reply_rate_pct and median_reply_hours, counted among the reviews LLM Pulse holds for the profile, the newest ones from each monthly read, whatever the date window), and &#x60;view&#x3D;reviews&#x60; the reviews published in the window on those profiles; ratings and reviews come from a monthly read of each profile. &#x60;view&#x3D;own_citations&#x60; returns the raw citations of the connected profile only and stays empty until a profile is connected. For Reddit use /dimensions/owned_media/summary?provider&#x3D;reddit for the summary and /dimensions/reddit for cited-content tables. A team member also needs the YouTube Intelligence permission for provider&#x3D;youtube. Requires the Growth plan or above.

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
val view : kotlin.String = view_example // kotlin.String | Row shape; the allowed set depends on provider, and activity is available for each provider
val store : kotlin.String = store_example // kotlin.String | provider=mobile_apps only
val owned : kotlin.Boolean = true // kotlin.Boolean | Return only rows belonging to the account's own connected profile
val model : kotlin.String = model_example // kotlin.String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : OwnedMediaListResponse = apiInstance.listOwnedMedia(projectId, provider, page, perPage, view, store, owned, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)
    println(result)
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
| **provider** | **kotlin.String**| The platform to report on | [enum: youtube, instagram, facebook, tiktok, linkedin, mobile_apps, trustpilot] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **view** | **kotlin.String**| Row shape; the allowed set depends on provider, and activity is available for each provider | [optional] [enum: videos, channels, posts, profiles, own_citations, apps, brands, reviews, activity] |
| **store** | **kotlin.String**| provider&#x3D;mobile_apps only | [optional] [default to Store.google_play] [enum: google_play, app_store] |
| **owned** | **kotlin.Boolean**| Return only rows belonging to the account&#39;s own connected profile | [optional] |
| **model** | **kotlin.String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |
| **from** | **java.time.OffsetDateTime**| Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**OwnedMediaListResponse**](OwnedMediaListResponse.md)

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

<a id="listOwnedMediaCitingPrompts"></a>
# **listOwnedMediaCitingPrompts**
> OwnedMediaCitingPromptsResponse listOwnedMediaCitingPrompts(projectId, provider, page, perPage, url, profile, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List the answers citing an owned-media item

The drill-down behind one row of an Owned Media or YouTube Intelligence table. Pass exactly one of url (a post or video URL, any variant of it) or profile (a handle with or without @, a profile or channel URL, or the channel key the YouTube channels rows return). item describes it (title, image, owner, whether it is yours and its stats), citation_count and prompt_count count its citations in the window, and data lists the citing answers newest first, each with its prompt, answer id, model, country, language, execution date, a plain-text excerpt and its link in the app. It shows prompt and answer text, so a team member also needs the Prompts permission, and YouTube Intelligence for provider&#x3D;youtube. Defaults to the last 30 days. Requires the Growth plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = OwnedMediaCommunitiesApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val provider : kotlin.String = provider_example // kotlin.String | The platform the item belongs to
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val url : kotlin.String = url_example // kotlin.String | A post or video URL, or a profile or channel URL. Exclusive with profile
val profile : kotlin.String = profile_example // kotlin.String | A handle (with or without @), a profile or channel URL, or a YouTube channel key (handle:..., channel:... or name:...). Exclusive with url
val model : kotlin.String = model_example // kotlin.String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : OwnedMediaCitingPromptsResponse = apiInstance.listOwnedMediaCitingPrompts(projectId, provider, page, perPage, url, profile, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling OwnedMediaCommunitiesApi#listOwnedMediaCitingPrompts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling OwnedMediaCommunitiesApi#listOwnedMediaCitingPrompts")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **provider** | **kotlin.String**| The platform the item belongs to | [enum: youtube, instagram, facebook, tiktok, linkedin] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **url** | **kotlin.String**| A post or video URL, or a profile or channel URL. Exclusive with profile | [optional] |
| **profile** | **kotlin.String**| A handle (with or without @), a profile or channel URL, or a YouTube channel key (handle:..., channel:... or name:...). Exclusive with url | [optional] |
| **model** | **kotlin.String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |
| **from** | **java.time.OffsetDateTime**| Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**OwnedMediaCitingPromptsResponse**](OwnedMediaCitingPromptsResponse.md)

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

Which Reddit content AI answers cite for your tracked prompts. view&#x3D;subreddits (default) returns one row per subreddit with its citation count, unique authors and positive/negative sentiment split; view&#x3D;authors returns one row per author; view&#x3D;threads returns the individual cited threads with upvotes, comments, average position and dominant sentiment. view&#x3D;breakdowns returns the figures behind Reddit Intelligence &gt; Sentiment and breakdowns: citations is the number of Reddit citations after the filters, and each row is one slice, with breakdown (sentiment, model or country), key, count and pct, the share within its breakdown as the page charts it. Sentiment is that of the AI answer that cited Reddit, with all five labels (very_positive to very_negative) listed, zero included; order and direction do not apply. Requires the Growth plan or above.

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
val brand : kotlin.String = brand_example // kotlin.String | Filter to citations whose scraped Reddit content mentions a brand: 'brand' for the tracked brand, or a competitor id. Reads the page content, not the AI answer. Any other value, or an id that names no competitor of the project, returns 422 ERR_INVALID_PARAM.
val order : kotlin.String = order_example // kotlin.String | Sort field; the allowed set depends on view, and view=breakdowns accepts none
val direction : kotlin.String = direction_example // kotlin.String | 
val model : kotlin.String = model_example // kotlin.String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
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
| **view** | **kotlin.String**|  | [optional] [default to View.subreddits] [enum: subreddits, authors, threads, breakdowns] |
| **subreddit** | **kotlin.String**| Filter to one subreddit (name without the r/ prefix) | [optional] |
| **author** | **kotlin.String**| Filter to one Reddit author | [optional] |
| **status** | **kotlin.String**| view&#x3D;threads only | [optional] [enum: open, archived] |
| **owned** | **kotlin.Boolean**| Return only subreddits/authors the account has claimed as its own | [optional] |
| **brand** | **kotlin.String**| Filter to citations whose scraped Reddit content mentions a brand: &#39;brand&#39; for the tracked brand, or a competitor id. Reads the page content, not the AI answer. Any other value, or an id that names no competitor of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **order** | **kotlin.String**| Sort field; the allowed set depends on view, and view&#x3D;breakdowns accepts none | [optional] [enum: citations, subreddit, unique_authors, positive_pct, negative_pct, author, avg_position, upvotes, comments, sentiment] |
| **direction** | **kotlin.String**|  | [optional] [default to Direction.desc] [enum: asc, desc] |
| **model** | **kotlin.String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |
| **from** | **java.time.OffsetDateTime**| Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
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

<a id="updateOwnedMediaProfiles"></a>
# **updateOwnedMediaProfiles**
> OwnedMediaProfilesUpdateResponse updateOwnedMediaProfiles(id, updateOwnedMediaProfilesRequest)

Update a project&#39;s owned-media profiles

Sets the profiles whose citations count as yours, like Project Settings &gt; Brand channels. Send only the fields to change: a URL field takes a URL, or an empty string or null to clear it, and every list REPLACES the stored one ([] clears it). URLs are normalized like the app (a profile URL is stored in its canonical form, a Google Play package name becomes its listing URL), and anything the app would refuse (a URL from another platform, an extra profile equal to the main one, more than 10 extra profiles, a malformed subreddit) is rejected with ERR_INVALID_PARAM and nothing is applied. A new main or extra profile is scraped in the background for its name and avatar, listed in profile_scrapes_queued. The response is the GET payload after the change. A team member needs the Owned Media create permission, YouTube Intelligence create to change the YouTube channel, and Projects update to change the extra profile or Reddit lists. Requires the Growth plan or above and a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = OwnedMediaCommunitiesApi()
val id : kotlin.Int = 56 // kotlin.Int | Project ID
val updateOwnedMediaProfilesRequest : UpdateOwnedMediaProfilesRequest =  // UpdateOwnedMediaProfilesRequest | 
try {
    val result : OwnedMediaProfilesUpdateResponse = apiInstance.updateOwnedMediaProfiles(id, updateOwnedMediaProfilesRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling OwnedMediaCommunitiesApi#updateOwnedMediaProfiles")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling OwnedMediaCommunitiesApi#updateOwnedMediaProfiles")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**| Project ID | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updateOwnedMediaProfilesRequest** | [**UpdateOwnedMediaProfilesRequest**](UpdateOwnedMediaProfilesRequest.md)|  | |

### Return type

[**OwnedMediaProfilesUpdateResponse**](OwnedMediaProfilesUpdateResponse.md)

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

