
# CustomReportDetailResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **id** | **kotlin.Int** |  |  |
| **name** | **kotlin.String** |  |  |
| **dateRange** | [**CustomReportDateRange**](CustomReportDateRange.md) |  |  |
| **schedule** | [**CustomReportSchedule**](CustomReportSchedule.md) |  |  |
| **filters** | [**CustomReportFilters**](CustomReportFilters.md) |  |  |
| **generatedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **blocks** | [**kotlin.collections.List&lt;CustomReportBlock&gt;**](CustomReportBlock.md) | The report layout in order |  |
| **widgets** | [**kotlin.collections.List&lt;CustomReportWidget&gt;**](CustomReportWidget.md) |  |  |
| **requestId** | **kotlin.String** |  |  |
| **recipientsCount** | **kotlin.Int** |  |  [optional] |
| **published** | **kotlin.Boolean** |  |  [optional] |
| **publicLinkActive** | **kotlin.Boolean** |  |  [optional] |
| **passwordProtected** | **kotlin.Boolean** |  |  [optional] |
| **portalOnly** | **kotlin.Boolean** |  |  [optional] |
| **lastSentAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the report was last emailed, on its schedule or with Send now |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **updatedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **comparePrevious** | **kotlin.Boolean** |  |  [optional] |
| **attachExcel** | **kotlin.Boolean** |  |  [optional] |
| **manualSendAvailableAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the 10-minute cooldown after the last manual send ends; null when none is running |  [optional] |



