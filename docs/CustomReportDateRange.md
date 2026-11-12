
# CustomReportDateRange

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **type** | [**inline**](#Type) | rolling (the last range_days days), previous_month (the previous calendar month), previous_3_months (the 3 calendar months before the current one) or custom (fixed dates, custom_from to custom_to) |  |
| **rangeDays** | **kotlin.Int** | Length of a rolling window; null for the other types |  |
| **customFrom** | [**java.time.LocalDate**](java.time.LocalDate.md) | First day chosen for a custom range; null for the other types |  |
| **customTo** | [**java.time.LocalDate**](java.time.LocalDate.md) | Last day chosen for a custom range, which can be after today; null for the other types |  |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) | First day of the window as of now (detail only) |  [optional] |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) | Last day of the window as of now (detail only); a custom range stops at today |  [optional] |
| **label** | **kotlin.String** | The window as the report shows it (detail only) |  [optional] |


<a id="Type"></a>
## Enum: type
| Name | Value |
| ---- | ----- |
| type | rolling, previous_month, previous_3_months, custom |



