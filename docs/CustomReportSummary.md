
# CustomReportSummary

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **name** | **kotlin.String** |  |  |
| **dateRange** | [**CustomReportDateRange**](CustomReportDateRange.md) |  |  |
| **schedule** | [**CustomReportSchedule**](CustomReportSchedule.md) |  |  |
| **recipientsCount** | **kotlin.Int** |  |  |
| **published** | **kotlin.Boolean** | Whether the shared link is published |  |
| **publicLinkActive** | **kotlin.Boolean** | Whether the shared link opens (published, not made inside a client portal, and the account is active on the Scale tier or higher) |  |
| **passwordProtected** | **kotlin.Boolean** |  |  |
| **portalOnly** | **kotlin.Boolean** | Made inside a client portal, so it cannot be shared or emailed |  |
| **widgetCount** | **kotlin.Int** |  |  |
| **widgets** | [**kotlin.collections.List&lt;CustomReportWidgetRef&gt;**](CustomReportWidgetRef.md) |  |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **updatedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **lastSentAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the report was last emailed, on its schedule or with Send now |  [optional] |



