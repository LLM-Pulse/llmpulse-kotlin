
# SearchConsoleAiVisibilityGapsResponseDataInner

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **query** | **kotlin.String** |  |  [optional] |
| **impressions** | **kotlin.Int** |  |  [optional] |
| **clicks** | **kotlin.Int** |  |  [optional] |
| **ctr** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | 0..1 fraction |  [optional] |
| **position** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Impression-weighted average position |  [optional] |
| **promptId** | **kotlin.Int** | The project&#39;s prompt with the same text as the query; null when no prompt matches |  [optional] |
| **responses** | **kotlin.Int** | AI answers the matching prompt got in the window over the account&#39;s enabled models; null when no prompt matches |  [optional] |
| **brandVisibility** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Brand Visibility of the matching prompt in the window, percent (0-100) of its AI answers that mention the brand, over the account&#39;s enabled models; null when no prompt matches or it has no answer |  [optional] |



