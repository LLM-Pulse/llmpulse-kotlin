
# SearchConsoleTimeseriesResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **&#x60;property&#x60;** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  |  [optional] |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  [optional] |
| **dataThrough** | [**java.time.LocalDate**](java.time.LocalDate.md) | Latest date Google has published for the property (it lags 2-3 days). Later days are missing, not zero. |  [optional] |
| **granularity** | **kotlin.String** |  |  [optional] |
| **&#x60;data&#x60;** | [**kotlin.collections.List&lt;SearchConsoleTimeseriesResponseDataInner&gt;**](SearchConsoleTimeseriesResponseDataInner.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



