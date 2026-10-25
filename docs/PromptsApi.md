# PromptsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**acceptSuggestedPrompts**](PromptsApi.md#acceptSuggestedPrompts) | **POST** /suggested_prompts/accept | Accept suggested prompts |
| [**createPromptGeneration**](PromptsApi.md#createPromptGeneration) | **POST** /prompt_generations | Generate prompt suggestions |
| [**createPrompts**](PromptsApi.md#createPrompts) | **POST** /prompts | Bulk-create prompts |
| [**deletePrompt**](PromptsApi.md#deletePrompt) | **DELETE** /prompts/{id} | Delete a prompt |
| [**getPromptGeneration**](PromptsApi.md#getPromptGeneration) | **GET** /prompt_generations/{id} | Get a prompt generation run |
| [**importPrompts**](PromptsApi.md#importPrompts) | **POST** /prompts/import | Import prompts |
| [**listPromptExecutions**](PromptsApi.md#listPromptExecutions) | **GET** /dimensions/prompt_executions | List prompt executions |
| [**listPrompts**](PromptsApi.md#listPrompts) | **GET** /dimensions/prompts | List prompts |
| [**listQueryFanOuts**](PromptsApi.md#listQueryFanOuts) | **GET** /dimensions/query_fan_outs | List query fan-out |
| [**listSuggestedPrompts**](PromptsApi.md#listSuggestedPrompts) | **GET** /suggested_prompts | List suggested prompts |
| [**rejectSuggestedPrompts**](PromptsApi.md#rejectSuggestedPrompts) | **POST** /suggested_prompts/reject | Reject suggested prompts |
| [**updatePrompt**](PromptsApi.md#updatePrompt) | **PATCH** /prompts/{id} | Edit a prompt&#39;s categorization |


<a id="acceptSuggestedPrompts"></a>
# **acceptSuggestedPrompts**
> SuggestedPromptsAcceptResponse acceptSuggestedPrompts(suggestedPromptsAcceptRequest)

Accept suggested prompts

Starts tracking up to 100 pending suggestions: each becomes a prompt in its own country and language, optionally put in one tag (tag_ids or tag_names; create_missing creates a missing name when the team member may create tags). Suggestions that are no longer pending come back in skipped. When the new prompts would exceed the plan the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val suggestedPromptsAcceptRequest : SuggestedPromptsAcceptRequest =  // SuggestedPromptsAcceptRequest | 
try {
    val result : SuggestedPromptsAcceptResponse = apiInstance.acceptSuggestedPrompts(suggestedPromptsAcceptRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#acceptSuggestedPrompts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#acceptSuggestedPrompts")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **suggestedPromptsAcceptRequest** | [**SuggestedPromptsAcceptRequest**](SuggestedPromptsAcceptRequest.md)|  | |

### Return type

[**SuggestedPromptsAcceptResponse**](SuggestedPromptsAcceptResponse.md)

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

<a id="createPromptGeneration"></a>
# **createPromptGeneration**
> PromptGenerationResponse createPromptGeneration(promptGenerationRequest)

Generate prompt suggestions

Starts a suggestion run with one of the generators behind the app&#39;s Add prompts wizards and answers 202 with the run. website writes suggestions from the scraped website (80% non-brand, 20% brand; up to 100 per project, then ERR_LIMIT_REACHED), keyword from a keyword or the project profile (optionally around a competitor), topic from a topic, reddit from Reddit discussions of a topic or brand, paa from Google People Also Ask (up to 5 keywords, counted against the account&#39;s 24-hour lookup allowance), reputational from brand reputation questions, translate from the project&#39;s prompts of another locale, search_console from the connected property&#39;s top queries of the last 28 days (Growth plan or above, ERR_PLAN_REQUIRED). The suggestions land in the Suggested prompts queue; poll GET /prompt_generations/{id}, then accept the ones you want with POST /suggested_prompts/accept. Nothing is tracked until accepted. The request is validated before the run starts, and refused with ERR_LIMIT_REACHED when the plan has no prompt slot left, or ERR_QUOTA_EXCEEDED after 60 runs in an hour (the per-user prompt suggestion allowance, shared with project setup). Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val promptGenerationRequest : PromptGenerationRequest =  // PromptGenerationRequest | 
try {
    val result : PromptGenerationResponse = apiInstance.createPromptGeneration(promptGenerationRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#createPromptGeneration")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#createPromptGeneration")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **promptGenerationRequest** | [**PromptGenerationRequest**](PromptGenerationRequest.md)|  | |

### Return type

[**PromptGenerationResponse**](PromptGenerationResponse.md)

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

<a id="createPrompts"></a>
# **createPrompts**
> PromptsCreateResponse createPrompts(promptsCreateRequest)

Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. When the project does not run on the schedule (paused, or beyond the plan&#39;s project limit) the prompts are still created, and the response says so with &#x60;tracked&#x60; false, &#x60;untracked_reason&#x60; and a &#x60;warning&#x60;. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val promptsCreateRequest : PromptsCreateRequest =  // PromptsCreateRequest | 
try {
    val result : PromptsCreateResponse = apiInstance.createPrompts(promptsCreateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#createPrompts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#createPrompts")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **promptsCreateRequest** | [**PromptsCreateRequest**](PromptsCreateRequest.md)|  | |

### Return type

[**PromptsCreateResponse**](PromptsCreateResponse.md)

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

<a id="deletePrompt"></a>
# **deletePrompt**
> deletePrompt(id, projectId)

Delete a prompt

Deletes a prompt (irreversible). The prompt disappears immediately and frees a prompt slot; its historical data (executions, mentions, citations, sentiment) is purged by a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.deletePrompt(id, projectId)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#deletePrompt")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#deletePrompt")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
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

<a id="getPromptGeneration"></a>
# **getPromptGeneration**
> PromptGenerationResponse getPromptGeneration(id, projectId)

Get a prompt generation run

Returns a run started with POST /prompt_generations: processing while the generator works, then completed with the suggestions it saved to the Suggested prompts queue, or failed with an error code and message. Poll every few seconds; most runs finish within a minute. Runs are kept for 24 hours, their suggestions stay in the queue.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val id : java.util.UUID = 38400000-8cf0-11bd-b23e-10b96e4ef00d // java.util.UUID | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    val result : PromptGenerationResponse = apiInstance.getPromptGeneration(id, projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#getPromptGeneration")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#getPromptGeneration")
    e.printStackTrace()
}
```

### Parameters
| **id** | **java.util.UUID**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

### Return type

[**PromptGenerationResponse**](PromptGenerationResponse.md)

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

<a id="importPrompts"></a>
# **importPrompts**
> PromptsImportResponse importPrompts(promptsImportRequest)

Import prompts

The app&#39;s CSV import as JSON: up to 500 rows, each with its own prompt, country_code, language_code (codes or names; both default to the project&#39;s) and tags, created when missing. Duplicates are skipped and existing prompts still get the row&#39;s tags. The prompt limits are checked before anything is written: when the new prompts would exceed the plan the call returns ERR_LIMIT_REACHED and imports nothing. A row is skipped and comes back in row_errors when its country or language is unknown, when it would give a prompt more than 50 tags (rows repeating a prompt add up) or when its tags would take the request past 500 new tags. For a team member without create access to Tags, a row that needs a tag that does not exist yet is skipped and comes back in row_errors. For a team member without update access to Prompts, a row matching a prompt that already existed adds no tags to it, and comes back in row_errors when it would have added one. Responds 201 when it created prompts, 200 otherwise. &#x60;tracked&#x60; false, with &#x60;untracked_reason&#x60; and a &#x60;warning&#x60;, means the project does not run on the schedule, so the imported prompts do not run until that changes. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val promptsImportRequest : PromptsImportRequest =  // PromptsImportRequest | 
try {
    val result : PromptsImportResponse = apiInstance.importPrompts(promptsImportRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#importPrompts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#importPrompts")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **promptsImportRequest** | [**PromptsImportRequest**](PromptsImportRequest.md)|  | |

### Return type

[**PromptsImportResponse**](PromptsImportResponse.md)

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

<a id="listPromptExecutions"></a>
# **listPromptExecutions**
> PromptExecutionsResponse listPromptExecutions(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, mentionFilter, citationFilter, competitors, output, promptType, brandKind)

List prompt executions

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val model : kotlin.String = model_example // kotlin.String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val mentionFilter : kotlin.String = mentionFilter_example // kotlin.String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
val citationFilter : kotlin.String = citationFilter_example // kotlin.String | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
val competitors : kotlin.String = competitors_example // kotlin.String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
try {
    val result : PromptExecutionsResponse = apiInstance.listPromptExecutions(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, mentionFilter, citationFilter, competitors, output, promptType, brandKind)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#listPromptExecutions")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#listPromptExecutions")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **model** | **kotlin.String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **mentionFilter** | **kotlin.String**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] [enum: mentions_you, not_mentions_you, mentions_competitor, not_mentions_competitor, you_and_competitor, competitor_not_you, you_not_competitor, no_brands] |
| **citationFilter** | **kotlin.String**| Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional] [enum: cites_you, not_cites_you, cites_competitor, not_cites_competitor, you_and_competitor, competitor_not_you, you_not_competitor, cites_no_brands] |
| **competitors** | **kotlin.String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |

### Return type

[**PromptExecutionsResponse**](PromptExecutionsResponse.md)

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

<a id="listPrompts"></a>
# **listPrompts**
> PromptsResponse listPrompts(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, from, to, output)

List prompts

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val model : kotlin.String = model_example // kotlin.String | Keep only the prompts with at least one execution on this AI model, of any outcome and date (the prompts /dimensions/prompt_executions lists for the same model). Prompts have no model of their own, so a prompt with no execution on this model yet (a newly enabled model, or a locale the model does not cover) is left out. An unknown value, or a model the API key's user has not enabled, returns 422 ERR_INVALID_PARAM. from and to still filter prompt creation.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : PromptsResponse = apiInstance.listPrompts(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, from, to, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#listPrompts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#listPrompts")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **model** | **kotlin.String**| Keep only the prompts with at least one execution on this AI model, of any outcome and date (the prompts /dimensions/prompt_executions lists for the same model). Prompts have no model of their own, so a prompt with no execution on this model yet (a newly enabled model, or a locale the model does not cover) is left out. An unknown value, or a model the API key&#39;s user has not enabled, returns 422 ERR_INVALID_PARAM. from and to still filter prompt creation. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**PromptsResponse**](PromptsResponse.md)

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

<a id="listQueryFanOuts"></a>
# **listQueryFanOuts**
> listQueryFanOuts(projectId, page, perPage, view, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)

List query fan-out

The sub-queries a model actually issued when answering your tracked prompts. view&#x3D;query (default) returns one row per distinct sub-query with count and share of all occurrences; view&#x3D;prompt returns one row per prompt with how many distinct sub-queries it produced. Fan-out is reported mainly by ChatGPT, so an empty result usually means the models in scope do not expose it. The API returns the aggregation only: for a period-over-period delta, call it twice with explicit from/to.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val view : kotlin.String = view_example // kotlin.String | Row shape: one per distinct sub-query, or one per prompt
val order : kotlin.String = order_example // kotlin.String | Sort field; the allowed set depends on view
val direction : kotlin.String = direction_example // kotlin.String | 
val query : kotlin.String = query_example // kotlin.String | Case-insensitive substring filter on the sub-query text
val model : kotlin.String = model_example // kotlin.String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
val collectionId : kotlin.String = 12,34 // kotlin.String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listQueryFanOuts(projectId, page, perPage, view, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#listQueryFanOuts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#listQueryFanOuts")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **view** | **kotlin.String**| Row shape: one per distinct sub-query, or one per prompt | [optional] [default to View.query] [enum: query, prompt] |
| **order** | **kotlin.String**| Sort field; the allowed set depends on view | [optional] [enum: count, share, query_text, total_count, variations_count, prompt_text] |
| **direction** | **kotlin.String**|  | [optional] [default to Direction.desc] [enum: asc, desc] |
| **query** | **kotlin.String**| Case-insensitive substring filter on the sub-query text | [optional] |
| **model** | **kotlin.String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **kotlin.String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
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

<a id="listSuggestedPrompts"></a>
# **listSuggestedPrompts**
> SuggestedPromptsResponse listSuggestedPrompts(projectId, source, status, page, perPage)

List suggested prompts

Lists the project&#39;s Suggested prompts queue, the same list the app&#39;s Suggested Prompts tab shows, oldest first. It holds the suggestions of every generator (website, magic for keyword runs, topic, reddit, paa, reputational, translate, gsc for Search Console, catalog). Pending suggestions by default; status&#x3D;all also returns accepted (with the prompt they became) and rejected ones. Team members need create access to Prompts, like the app&#39;s tab.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val source : kotlin.String = source_example // kotlin.String | Only suggestions from this generator
val status : kotlin.String = status_example // kotlin.String | Only suggestions in this status
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    val result : SuggestedPromptsResponse = apiInstance.listSuggestedPrompts(projectId, source, status, page, perPage)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#listSuggestedPrompts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#listSuggestedPrompts")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **source** | **kotlin.String**| Only suggestions from this generator | [optional] [enum: website, magic, paa, topic, reddit, reputational, gsc, translate, catalog] |
| **status** | **kotlin.String**| Only suggestions in this status | [optional] [default to Status.pending] [enum: pending, accepted, rejected, all] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**|  | [optional] [default to 50] |

### Return type

[**SuggestedPromptsResponse**](SuggestedPromptsResponse.md)

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

<a id="rejectSuggestedPrompts"></a>
# **rejectSuggestedPrompts**
> SuggestedPromptsRejectResponse rejectSuggestedPrompts(suggestedPromptIdsRequest)

Reject suggested prompts

Marks up to 100 pending suggestions as rejected, so they leave the pending list; suggestions that are no longer pending stay as they are. Tracks and deletes nothing. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val suggestedPromptIdsRequest : SuggestedPromptIdsRequest =  // SuggestedPromptIdsRequest | 
try {
    val result : SuggestedPromptsRejectResponse = apiInstance.rejectSuggestedPrompts(suggestedPromptIdsRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#rejectSuggestedPrompts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#rejectSuggestedPrompts")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **suggestedPromptIdsRequest** | [**SuggestedPromptIdsRequest**](SuggestedPromptIdsRequest.md)|  | |

### Return type

[**SuggestedPromptsRejectResponse**](SuggestedPromptsRejectResponse.md)

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

<a id="updatePrompt"></a>
# **updatePrompt**
> PromptCategorizationResponse updatePrompt(id, updatePromptRequest)

Edit a prompt&#39;s categorization

Manual categorization, exactly like editing the intent and brand badges on the prompt page: send &#x60;prompt_type&#x60;, &#x60;brand_kind&#x60; or both. The prompt is marked as manually categorized (&#x60;categorization_source&#x60; becomes &#x60;manual&#x60;), so automatic categorization no longer changes it; the prompt page can revert it to automatic. Any other field returns ERR_INVALID_PARAM. Not available from a white-label portal (ERR_INTEGRATION_UNAVAILABLE), where the page hides the editor. Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on Prompts.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = PromptsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val updatePromptRequest : UpdatePromptRequest =  // UpdatePromptRequest | 
try {
    val result : PromptCategorizationResponse = apiInstance.updatePrompt(id, updatePromptRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PromptsApi#updatePrompt")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PromptsApi#updatePrompt")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updatePromptRequest** | [**UpdatePromptRequest**](UpdatePromptRequest.md)|  | |

### Return type

[**PromptCategorizationResponse**](PromptCategorizationResponse.md)

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

