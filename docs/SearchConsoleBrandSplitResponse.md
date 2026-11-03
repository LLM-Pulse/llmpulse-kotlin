
# SearchConsoleBrandSplitResponse

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
| **brandTerms** | **kotlin.collections.List&lt;kotlin.String&gt;** | The project&#39;s brand name, matching names, app names and domain, lowercased, each matched as a whole word |  [optional] |
| **totals** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  |  [optional] |
| **branded** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  |  [optional] |
| **nonBranded** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  |  [optional] |
| **unclassified** | [**SearchConsoleBrandSplitResponseUnclassified**](SearchConsoleBrandSplitResponseUnclassified.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



