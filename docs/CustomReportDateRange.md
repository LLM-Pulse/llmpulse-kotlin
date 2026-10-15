
# CustomReportDateRange

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **type** | [**inline**](#Type) | rolling (the last range_days days) or previous_month (the previous calendar month) |  |
| **rangeDays** | **kotlin.Int** | Length of a rolling window; null for previous_month |  |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) | First day of the window as of now (detail only) |  [optional] |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) | Last day of the window as of now (detail only) |  [optional] |
| **label** | **kotlin.String** | The window as the report shows it (detail only) |  [optional] |


<a id="Type"></a>
## Enum: type
| Name | Value |
| ---- | ----- |
| type | rolling, previous_month |



