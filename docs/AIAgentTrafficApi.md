# AIAgentTrafficApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAgentTraffic**](AIAgentTrafficApi.md#getAgentTraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale plan or above, Beta) |
| [**getAiTraffic**](AIAgentTrafficApi.md#getAiTraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale plan or above) |
| [**listAgentBots**](AIAgentTrafficApi.md#listAgentBots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above) |


<a id="getAgentTraffic"></a>
# **getAgentTraffic**
> AgentTrafficResponse getAgentTraffic(projectId, range, from, to, bot, company, groupBy, granularity)

AI bot crawler traffic (Scale plan or above, Beta)

Aggregated AI bot traffic hitting the project&#39;s origin server (GPTBot, PerplexityBot, ClaudeBot, OAI-SearchBot, Google-Extended, etc.). Sourced from Cloudflare or CSV uploads. Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AIAgentTrafficApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val bot : kotlin.String = bot_example // kotlin.String | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot)
val company : kotlin.String = company_example // kotlin.String | Filter by company (e.g. openai, anthropic, google)
val groupBy : kotlin.String = groupBy_example // kotlin.String | 
val granularity : kotlin.String = granularity_example // kotlin.String | 
try {
    val result : AgentTrafficResponse = apiInstance.getAgentTraffic(projectId, range, from, to, bot, company, groupBy, granularity)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling AIAgentTrafficApi#getAgentTraffic")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AIAgentTrafficApi#getAgentTraffic")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **bot** | **kotlin.String**| Filter by bot slug (e.g. gptbot, claudebot, perplexitybot) | [optional] |
| **company** | **kotlin.String**| Filter by company (e.g. openai, anthropic, google) | [optional] |
| **groupBy** | **kotlin.String**|  | [optional] [default to GroupBy.bot] [enum: bot, company] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |

### Return type

[**AgentTrafficResponse**](AgentTrafficResponse.md)

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

<a id="getAiTraffic"></a>
# **getAiTraffic**
> getAiTraffic(projectId, range, from, to, source, granularity)

AI referral traffic (Scale plan or above)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AIAgentTrafficApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val source : kotlin.String = source_example // kotlin.String | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude)
val granularity : kotlin.String = granularity_example // kotlin.String | 
try {
    apiInstance.getAiTraffic(projectId, range, from, to, source, granularity)
} catch (e: ClientException) {
    println("4xx response calling AIAgentTrafficApi#getAiTraffic")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AIAgentTrafficApi#getAiTraffic")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **source** | **kotlin.String**| Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude) | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **granularity** | **kotlin.String**|  | [optional] [enum: day, week, month] |

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

<a id="listAgentBots"></a>
# **listAgentBots**
> AgentBotsResponse listAgentBots(projectId, output)

AI bot catalog (Scale plan or above)

Static catalog of AI bots that Agent Analytics can identify. Useful for rendering filter UIs that mirror our internal classification (slug, display name, company, category, Cloudflare verified-bot mapping, description). Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED. The equivalent MCP tool list_agent_bots is available on the Scale plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = AIAgentTrafficApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : AgentBotsResponse = apiInstance.listAgentBots(projectId, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling AIAgentTrafficApi#listAgentBots")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling AIAgentTrafficApi#listAgentBots")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**AgentBotsResponse**](AgentBotsResponse.md)

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

