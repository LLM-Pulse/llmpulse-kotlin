
# OwnedMediaSummaryActivityPeriod

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **date** | [**java.time.LocalDate**](java.time.LocalDate.md) | Start date of the actual reporting period |  |
| **citations** | **kotlin.Int** |  |  |
| **yours** | **kotlin.Int** | Citations on owned profiles and content, null for provider&#x3D;overview |  |
| **other** | **kotlin.Int** | Citations not counted as yours, null for provider&#x3D;overview |  |
| **positive** | **kotlin.Int** | Citations whose AI answer sentiment is positive |  [optional] |
| **neutral** | **kotlin.Int** | Citations whose AI answer sentiment is neutral or mixed |  [optional] |
| **negative** | **kotlin.Int** | Citations whose AI answer sentiment is negative |  [optional] |



