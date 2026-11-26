
# QueryFanOutRow

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **queryText** | **kotlin.String** | The sub-query a model issued (view&#x3D;query) |  [optional] |
| **count** | **kotlin.Int** | Times it was issued (view&#x3D;query) |  [optional] |
| **share** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Share of all sub-query occurrences, on a 0-100 scale (view&#x3D;query) |  [optional] |
| **promptId** | **kotlin.Int** | view&#x3D;prompt |  [optional] |
| **promptText** | **kotlin.String** | view&#x3D;prompt |  [optional] |
| **variationsCount** | **kotlin.Int** | Distinct sub-queries issued for the prompt (view&#x3D;prompt) |  [optional] |
| **totalCount** | **kotlin.Int** | Sub-queries issued for the prompt, repeats included (view&#x3D;prompt) |  [optional] |



