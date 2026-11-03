
# SearchConsoleOpportunitiesResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **&#x60;property&#x60;** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  |  [optional] |
| **properties** | [**kotlin.collections.List&lt;SearchConsoleProperty&gt;**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) |  [optional] |
| **excludedProperties** | [**kotlin.collections.List&lt;SearchConsoleExcludedProperty&gt;**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them |  [optional] |
| **propertyErrors** | [**kotlin.collections.List&lt;SearchConsolePropertyError&gt;**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures |  [optional] |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **dataThrough** | [**java.time.LocalDate**](java.time.LocalDate.md) | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. |  [optional] |
| **minImpressions** | **kotlin.Int** |  |  [optional] |
| **minPosition** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **maxPosition** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **topCtr** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | CTR (0..1) of the property&#39;s queries averaging position 3 or better in the window; null when there are none, and then no potential_clicks |  [optional] |
| **page** | **kotlin.Int** |  |  [optional] |
| **perPage** | **kotlin.Int** |  |  [optional] |
| **total** | **kotlin.Int** | Rows in the report before paging |  [optional] |
| **truncated** | **kotlin.Boolean** | Present (true) when Google returned its 25,000-row maximum for a property, so the report covers its top rows only |  [optional] |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;SearchConsoleOpportunitiesResponseDataInner&gt;**](SearchConsoleOpportunitiesResponseDataInner.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



