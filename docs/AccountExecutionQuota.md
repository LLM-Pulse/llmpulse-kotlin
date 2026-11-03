
# AccountExecutionQuota

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **limit** | **kotlin.Int** |  |  [optional] |
| **used** | **kotlin.Int** |  |  [optional] |
| **remaining** | **kotlin.Int** |  |  [optional] |
| **unlimited** | **kotlin.Boolean** |  |  [optional] |
| **period** | [**inline**](#Period) | The tracking window, from the account&#39;s tracking cadence (week runs Monday to Sunday) |  [optional] |
| **resetsAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the next window starts and the allowance is full again (00:00 Europe/Madrid) |  [optional] |


<a id="Period"></a>
## Enum: period
| Name | Value |
| ---- | ----- |
| period | day, week, month |



