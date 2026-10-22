
# SearchConsoleSummaryResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **&#x60;property&#x60;** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  |  [optional] |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **dataThrough** | [**java.time.LocalDate**](java.time.LocalDate.md) | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. |  [optional] |
| **totals** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  |  [optional] |
| **dimension** | **kotlin.String** | Present when a breakdown was requested |  [optional] |
| **breakdown** | [**kotlin.collections.List&lt;SearchConsoleSummaryResponseBreakdownInner&gt;**](SearchConsoleSummaryResponseBreakdownInner.md) | Present when a breakdown was requested, sorted by impressions descending |  [optional] |
| **breakdownTruncated** | **kotlin.Boolean** | Present (true) when limit or Google&#39;s 25,000-row maximum left breakdown rows out, so they add up to less than totals |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |
| **properties** | [**kotlin.collections.List&lt;SearchConsoleProperty&gt;**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) |  [optional] |
| **excludedProperties** | [**kotlin.collections.List&lt;SearchConsoleExcludedProperty&gt;**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them |  [optional] |
| **propertyErrors** | [**kotlin.collections.List&lt;SearchConsolePropertyError&gt;**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures |  [optional] |



