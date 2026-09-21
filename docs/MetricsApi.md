# MetricsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getPromptSummary**](MetricsApi.md#getPromptSummary) | **GET** /metrics/prompt_summary | Per-prompt metrics summary |
| [**getShareOfVoice**](MetricsApi.md#getShareOfVoice) | **GET** /metrics/sov | Share of Voice |
| [**getSummary**](MetricsApi.md#getSummary) | **GET** /metrics/summary | Aggregated metrics summary |
| [**getTimeseries**](MetricsApi.md#getTimeseries) | **GET** /metrics/timeseries | Time-series metrics |
| [**getTopSources**](MetricsApi.md#getTopSources) | **GET** /metrics/top_sources | Top cited sources |


<a id="getPromptSummary"></a>
# **getPromptSummary**
> PromptSummaryResponse getPromptSummary(projectId, range, from, to, breakdown, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, sortDir, page, perPage, output)

Per-prompt metrics summary

Paginated per-prompt aggregated metrics. Returns responses, mentions, citations, mention_rate, citation_rate, avg_mention_position and avg_position per prompt. Citations and citation rate include visible citations and background source references; avg_position uses visible citations only. Pass &#x60;breakdown&#x3D;model&#x60; to split each prompt by model.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = MetricsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val breakdown : kotlin.String = breakdown_example // kotlin.String | Add per-(prompt, model) rows to the output
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val sort : kotlin.String = sort_example // kotlin.String | 
val sortDir : kotlin.String = sortDir_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : PromptSummaryResponse = apiInstance.getPromptSummary(projectId, range, from, to, breakdown, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, sortDir, page, perPage, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling MetricsApi#getPromptSummary")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling MetricsApi#getPromptSummary")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **breakdown** | **kotlin.String**| Add per-(prompt, model) rows to the output | [optional] [enum: model] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **sort** | **kotlin.String**|  | [optional] [default to Sort.responses] [enum: responses, mentions, citations, mention_rate, visibility, citation_rate, avg_mention_position, avg_position] |
| **sortDir** | **kotlin.String**|  | [optional] [default to SortDir.desc] [enum: asc, desc] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**PromptSummaryResponse**](PromptSummaryResponse.md)

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

<a id="getShareOfVoice"></a>
# **getShareOfVoice**
> SovResponse getShareOfVoice(projectId, range, from, to, granularity, competitors, model, collectionId, prompt, promptType, brandKind, output, view)

Share of Voice

Share of Voice breakdown comparing your project to competitors. Returns over_time, current snapshot, and a Top-4 + Others breakdown.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = MetricsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val granularity : kotlin.String = granularity_example // kotlin.String | 
val competitors : kotlin.String = competitors_example // kotlin.String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
val view : kotlin.String = view_example // kotlin.String | Which Share of Voice projection to flatten. Only valid together with 'output'. 'over_time' (default) is one row per date and actor, 'current' the ranked snapshot, 'breakdown' the Top 4 plus Others.
try {
    val result : SovResponse = apiInstance.getShareOfVoice(projectId, range, from, to, granularity, competitors, model, collectionId, prompt, promptType, brandKind, output, view)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling MetricsApi#getShareOfVoice")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling MetricsApi#getShareOfVoice")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |
| **competitors** | **kotlin.String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **view** | **kotlin.String**| Which Share of Voice projection to flatten. Only valid together with &#39;output&#39;. &#39;over_time&#39; (default) is one row per date and actor, &#39;current&#39; the ranked snapshot, &#39;breakdown&#39; the Top 4 plus Others. | [optional] [default to View.over_time] [enum: over_time, current, breakdown] |

### Return type

[**SovResponse**](SovResponse.md)

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

<a id="getSummary"></a>
# **getSummary**
> SummaryResponse getSummary(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, prompt, promptType, brandKind, output)

Aggregated metrics summary

Same as /metrics/timeseries but adds a &#x60;summary&#x60; block with total/min/max/last per metric per actor, plus a &#x60;position_distribution&#x60; block (Position 1, Position 2, Position 3+). Citations and citation rate include visible citations and background source references. Background references use position 0 and are excluded from avg_position and position distributions. &#x60;total&#x60; is a SUM for count metrics (mentions, citations, responses) and an AVERAGE across periods for rate/percentage and average metrics (visibility/mention_rate, citation_rate, ai_visibility_score, sentiment shares, avg_position, avg_mention_position, net_sentiment); rates are never summed. Each summary row carries an &#x60;aggregation&#x60; field (&#x60;sum&#x60; or &#x60;average&#x60;).

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = MetricsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val metrics : kotlin.String = metrics_example // kotlin.String | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only.
val granularity : kotlin.String = granularity_example // kotlin.String | 
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val competitors : kotlin.String = competitors_example // kotlin.String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : SummaryResponse = apiInstance.getSummary(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, prompt, promptType, brandKind, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling MetricsApi#getSummary")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling MetricsApi#getSummary")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **metrics** | **kotlin.String**| Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [optional] |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **competitors** | **kotlin.String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**SummaryResponse**](SummaryResponse.md)

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

<a id="getTimeseries"></a>
# **getTimeseries**
> TimeseriesResponse getTimeseries(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, includeProject, output)

Time-series metrics

Returns time-series data for one or more metrics, broken down by actor (project + competitors). Supports day/week/month granularity, with sticky carry-forward semantics for week/month aggregates.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = MetricsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val metrics : kotlin.String = metrics_example // kotlin.String | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only.
val granularity : kotlin.String = granularity_example // kotlin.String | 
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val competitors : kotlin.String = competitors_example // kotlin.String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val includeProject : kotlin.Boolean = true // kotlin.Boolean | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : TimeseriesResponse = apiInstance.getTimeseries(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, includeProject, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling MetricsApi#getTimeseries")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling MetricsApi#getTimeseries")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **metrics** | **kotlin.String**| Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [optional] |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **competitors** | **kotlin.String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **includeProject** | **kotlin.Boolean**|  | [optional] [default to true] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**TimeseriesResponse**](TimeseriesResponse.md)

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

<a id="getTopSources"></a>
# **getTopSources**
> TopSourcesResponse getTopSources(projectId, range, from, to, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, query, page, perPage, output)

Top cited sources

Registrable domains most frequently cited in AI responses for the project, including visible citations and background source references. This endpoint remains a domain rollup when exact-subdomain matching is enabled. Results can be sorted by total responses, average mention rate, or average visibility.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = MetricsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val sort : kotlin.String = sort_example // kotlin.String | 
val query : kotlin.String = query_example // kotlin.String | Filter domains by case-insensitive partial match
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : TopSourcesResponse = apiInstance.getTopSources(projectId, range, from, to, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, query, page, perPage, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling MetricsApi#getTopSources")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling MetricsApi#getTopSources")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **sort** | **kotlin.String**|  | [optional] [default to Sort.total_responses] [enum: total_responses, avg_mention_rate, avg_visibility] |
| **query** | **kotlin.String**| Filter domains by case-insensitive partial match | [optional] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**TopSourcesResponse**](TopSourcesResponse.md)

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

