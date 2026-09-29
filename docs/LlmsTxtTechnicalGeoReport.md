
# LlmsTxtTechnicalGeoReport

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  [optional] |
| **reportType** | **kotlin.String** | Always llms_txt |  [optional] |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **batchId** | **kotlin.Int** | Bundle the report was created in; null for a report created on its own |  [optional] |
| **url** | **kotlin.String** | Always null for llms_txt reports; domain names the website |  [optional] |
| **domain** | **kotlin.String** |  |  [optional] |
| **countryCode** | **kotlin.String** |  |  [optional] |
| **outputLanguageCode** | **kotlin.String** | ISO 639-1 code the files were requested in; null when they are written in the website&#39;s own language |  [optional] |
| **status** | **kotlin.String** |  |  [optional] |
| **resultAvailable** | **kotlin.Boolean** |  |  [optional] |
| **overallScore** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Always null for llms_txt reports |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **updatedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **resultData** | [**LlmsTxtTechnicalGeoReportResultData**](LlmsTxtTechnicalGeoReportResultData.md) |  |  [optional] |
| **errorMessage** | **kotlin.String** |  |  [optional] |
| **pollAfterSeconds** | **kotlin.Int** | Seconds to wait before polling again while the report runs; null once it has finished |  [optional] |
| **appUrl** | [**java.net.URI**](java.net.URI.md) | Opens this report in the app |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



