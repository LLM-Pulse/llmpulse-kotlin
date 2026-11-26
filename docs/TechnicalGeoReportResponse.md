
# TechnicalGeoReportResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **reportType** | **kotlin.String** | The report_type requested (agent_readiness for ai_readiness) |  |
| **projectId** | **kotlin.Int** |  |  |
| **batchId** | **kotlin.Int** | Bundle the report was created in; null for a report created on its own |  |
| **url** | **kotlin.String** | The page analysed; null for the domain-level types (robots_txt, agent_readiness, llms_txt, ai_visibility) |  |
| **domain** | **kotlin.String** |  |  |
| **countryCode** | **kotlin.String** | Set only on llms_txt and ai_visibility reports |  |
| **outputLanguageCode** | **kotlin.String** | ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website&#39;s own language and for every other type |  |
| **status** | **kotlin.String** | Depends on report_type. Every type ends completed or failed; ai_visibility can also end insufficient_data |  |
| **resultAvailable** | **kotlin.Boolean** | Whether status is completed |  |
| **overallScore** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Null until the report completes, and always for llms_txt |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **updatedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **resultData** | [**kotlin.collections.Map&lt;kotlin.String, kotlin.Any&gt;**](kotlin.Any.md) | The full result once the report has completed; null before that. Its shape depends on report_type; an llms_txt report returns its files as LlmsTxtTechnicalGeoReport describes |  |
| **errorMessage** | **kotlin.String** | Why the report failed, or why an ai_visibility report found insufficient data; null otherwise |  |
| **pollAfterSeconds** | **kotlin.Int** | Seconds to wait before polling again while the report runs; null once it has finished |  |
| **requestId** | **kotlin.String** |  |  |
| **appUrl** | [**java.net.URI**](java.net.URI.md) | Opens this report in the app |  [optional] |



