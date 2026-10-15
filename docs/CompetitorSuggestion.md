
# CompetitorSuggestion

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.String** | The suggestion key (brands) or the id of one citing source row (citations) |  |
| **domain** | **kotlin.String** |  |  |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** | The names a tracked competitor would be matched by; empty for a cited domain |  |
| **brandName** | **kotlin.String** | The proposed brand name; null for a cited domain |  [optional] |
| **mentions** | **kotlin.Int** | Answers naming the brand, when the discovery counted them (brands only) |  [optional] |
| **citations** | **kotlin.Int** | Answers citing the domain (citations only) |  [optional] |



