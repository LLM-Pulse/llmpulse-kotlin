
# AccountAgentUsage

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **percentUsed** | **kotlin.Int** | Whole percent used, rounded down, from 0 to 100; 100 means the allowance is spent and new questions wait until resets_on. null when unlimited is true |  [optional] |
| **unlimited** | **kotlin.Boolean** |  |  [optional] |
| **included** | **kotlin.Boolean** | Whether the plan includes the in-app AI assistant. false on a plan without it, where percent_used is 100 |  [optional] |
| **period** | **kotlin.String** | Always month |  [optional] |
| **resetsOn** | [**java.time.LocalDate**](java.time.LocalDate.md) | The first day of next month, when the allowance starts again |  [optional] |



