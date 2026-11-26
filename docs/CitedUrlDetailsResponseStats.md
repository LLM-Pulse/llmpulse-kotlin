
# CitedUrlDetailsResponseStats

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **totalResponses** | **kotlin.Int** | Answers citing the URL under the filters |  |
| **totalCitations** | **kotlin.Int** |  |  |
| **citationRate** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | total_responses as a percentage (0-100) of citation_rate_denominator |  |
| **citationRateDenominator** | **kotlin.Int** | Answers matching the filters |  |
| **avgCitationPosition** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Null when no visible citation has a rank |  |
| **firstSeenAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | Null when no citation matches the filters |  |
| **lastSeenAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | Null when no citation matches the filters |  |
| **distinctUrls** | **kotlin.Int** | Spellings of the URL cited (tracking parameters, a trailing slash) |  |
| **sourceTypes** | [**CitedUrlDetailsResponseStatsSourceTypes**](CitedUrlDetailsResponseStatsSourceTypes.md) |  |  |
| **models** | **kotlin.collections.Map&lt;kotlin.String, kotlin.Int&gt;** | Answers citing the URL per AI model, keyed by model |  |



