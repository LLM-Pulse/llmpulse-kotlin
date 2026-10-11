
# PromptSummaryRow

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **promptId** | **kotlin.Int** |  |  [optional] |
| **promptText** | **kotlin.String** |  |  [optional] |
| **model** | **kotlin.String** | Only present when breakdown&#x3D;model |  [optional] |
| **responses** | **kotlin.Int** |  |  [optional] |
| **mentions** | **kotlin.Int** |  |  [optional] |
| **citations** | **kotlin.Int** |  |  [optional] |
| **visibility** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **mentionRate** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **citationRate** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **avgMentionPosition** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **avgPosition** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **appUrl** | [**java.net.URI**](java.net.URI.md) | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project |  [optional] |
| **countryCode** | **kotlin.String** | Country of the prompt, as in /dimensions/prompts |  [optional] |
| **languageCode** | **kotlin.String** | Language of the prompt, as in /dimensions/prompts |  [optional] |
| **promptType** | **kotlin.String** | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified |  [optional] |
| **brandKind** | **kotlin.String** | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified |  [optional] |
| **tags** | [**kotlin.collections.List&lt;TagRef&gt;**](TagRef.md) | Every tag the prompt belongs to |  [optional] |
| **sentimentResponses** | **kotlin.Int** | Responses in the window with a sentiment verdict for the brand, the base of the sentiment percentages (deduplicated like the sentiment timeseries) |  [optional] |
| **sentimentVeryPositive** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Percentage (0-100) of sentiment_responses whose brand verdict is very positive; null when sentiment_responses is 0 |  [optional] |
| **sentimentPositive** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Percentage (0-100) of sentiment_responses whose brand verdict is positive; null when sentiment_responses is 0 |  [optional] |
| **sentimentNeutral** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Percentage (0-100) of sentiment_responses whose brand verdict is neutral; null when sentiment_responses is 0 |  [optional] |
| **sentimentNegative** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Percentage (0-100) of sentiment_responses whose brand verdict is negative; null when sentiment_responses is 0 |  [optional] |
| **sentimentVeryNegative** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Percentage (0-100) of sentiment_responses whose brand verdict is very negative; null when sentiment_responses is 0 |  [optional] |
| **netSentiment** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Positive minus negative percentages (-100 to 100), neutral counted in the base; null when sentiment_responses is 0 |  [optional] |



