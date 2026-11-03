
# AiModelSentimentRow

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **model** | **kotlin.String** | AI model key, as /dimensions/models lists it |  [optional] |
| **label** | **kotlin.String** | Display name of the model |  [optional] |
| **color** | **kotlin.String** | Hex color the app charts the model with |  [optional] |
| **sentimentsCount** | **kotlin.Int** | Brand sentiment verdicts in the model&#39;s answers |  [optional] |
| **positiveCount** | **kotlin.Int** | Positive and very positive verdicts |  [optional] |
| **negativeCount** | **kotlin.Int** | Negative and very negative verdicts |  [optional] |
| **netSentiment** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | positive_count minus negative_count as a percentage (-100 to 100) of sentiments_count, neutral verdicts counted in the base; null when sentiments_count is 0 |  [optional] |



