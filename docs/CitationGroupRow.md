
# CitationGroupRow

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **sourceId** | **kotlin.Int** | The group&#39;s first citation |  |
| **view** | **kotlin.String** | url, domain or host |  |
| **key** | **kotlin.String** | The URL as cited, the domain or the host |  |
| **totalResponses** | **kotlin.Int** | Answers citing it |  |
| **totalCitations** | **kotlin.Int** |  |  |
| **citationRate** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | total_responses as a percentage (0-100) of citation_rate_denominator |  |
| **citationRateDenominator** | **kotlin.Int** | Answers matching the filters |  |
| **avgCitationPosition** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Null when no visible citation has a rank |  |
| **firstSeenAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **lastSeenAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **models** | **kotlin.collections.Map&lt;kotlin.String, kotlin.Int&gt;** | Answers citing it per AI model, keyed by model |  |
| **url** | **kotlin.String** | url view only. The URL as cited |  [optional] |
| **urlSha256** | **kotlin.String** | url view only. Key of the cited page, shared by the URL&#39;s variants |  [optional] |
| **normalizedUrl** | **kotlin.String** | url view only |  [optional] |
| **pageCache** | [**CitationPageCache**](CitationPageCache.md) |  |  [optional] |
| **pageMentions** | [**CitationPageMentions**](CitationPageMentions.md) |  |  [optional] |
| **domain** | **kotlin.String** | domain view only |  [optional] |
| **host** | **kotlin.String** | host view only |  [optional] |
| **aggregateDetails** | [**CitationGroupRowAggregateDetails**](CitationGroupRowAggregateDetails.md) |  |  [optional] |
| **citationSeries** | [**CitationSeries**](CitationSeries.md) |  |  [optional] |



