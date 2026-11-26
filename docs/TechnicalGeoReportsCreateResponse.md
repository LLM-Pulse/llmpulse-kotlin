
# TechnicalGeoReportsCreateResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **url** | **kotlin.String** | The URL analysed |  |
| **countryCode** | **kotlin.String** | The country used, the project country when none was sent |  |
| **outputLanguageCode** | **kotlin.String** | ISO 639-1 code the llms.txt files are written in, or auto for the website&#39;s own language |  |
| **batchId** | **kotlin.Int** | Bundle id, for the batch_id filter of GET /technical_geo_reports; null when no report was created |  |
| **createdReports** | **kotlin.collections.List&lt;kotlin.String&gt;** | The report_type of every report created |  |
| **reportIds** | **kotlin.collections.Map&lt;kotlin.String, kotlin.Int&gt;** | The id of each created report, by report_type |  |
| **appUrls** | [**kotlin.collections.Map&lt;kotlin.String, java.net.URI&gt;**](java.net.URI.md) | The link that opens each created report in the app, by report_type |  |
| **failedReports** | [**kotlin.collections.List&lt;TechnicalGeoReportsCreateResponseFailedReportsInner&gt;**](TechnicalGeoReportsCreateResponseFailedReportsInner.md) | Reports that could not be created, with the reasons |  |
| **nextEndpoint** | **kotlin.String** | Path template to poll each created report |  |
| **pollAfterSeconds** | **kotlin.Int** | Seconds to wait before the first poll |  |
| **requestId** | **kotlin.String** |  |  |



