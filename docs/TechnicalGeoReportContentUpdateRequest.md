
# TechnicalGeoReportContentUpdateRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **reportType** | [**inline**](#ReportType) | Only llms_txt reports have editable content |  |
| **contentVersion** | **kotlin.String** | result_data.content_version of the report as last read. It changes on every save; a value that no longer matches is refused as stale |  |
| **edits** | [**TechnicalGeoReportContentUpdateRequestEdits**](TechnicalGeoReportContentUpdateRequestEdits.md) |  |  |


<a id="ReportType"></a>
## Enum: report_type
| Name | Value |
| ---- | ----- |
| reportType | llms_txt |



