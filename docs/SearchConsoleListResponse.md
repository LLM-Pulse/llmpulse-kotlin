
# SearchConsoleListResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **&#x60;property&#x60;** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  |  [optional] |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **dataThrough** | [**java.time.LocalDate**](java.time.LocalDate.md) | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. |  [optional] |
| **page** | **kotlin.Int** |  |  [optional] |
| **perPage** | **kotlin.Int** |  |  [optional] |
| **total** | **kotlin.Int** | Rows in this window (one Google request, at most 25,000) |  [optional] |
| **sort** | **kotlin.String** |  |  [optional] |
| **startRow** | **kotlin.Int** | Present when start_row was set |  [optional] |
| **truncated** | **kotlin.Boolean** | Present (true) when Google returned 25,000 rows, so more rows exist past this window |  [optional] |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;SearchConsoleListResponseDataInner&gt;**](SearchConsoleListResponseDataInner.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |
| **properties** | [**kotlin.collections.List&lt;SearchConsoleProperty&gt;**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) |  [optional] |
| **excludedProperties** | [**kotlin.collections.List&lt;SearchConsoleExcludedProperty&gt;**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them |  [optional] |
| **propertyErrors** | [**kotlin.collections.List&lt;SearchConsolePropertyError&gt;**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures |  [optional] |



