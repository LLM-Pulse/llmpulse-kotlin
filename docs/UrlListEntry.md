
# UrlListEntry

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **&#x60;value&#x60;** | **kotlin.String** | The exact URL, \&quot;host/path\&quot; of a prefix, or the host of a domain rule. |  |
| **matchType** | [**inline**](#MatchType) |  |  |
| **host** | **kotlin.String** |  |  |
| **status** | [**inline**](#Status) |  |  |
| **addedOn** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  |
| **cost** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  |
| **channel** | **kotlin.String** |  |  |
| **citations** | **kotlin.Int** |  |  |
| **citedPages** | **kotlin.Int** |  |  |
| **firstCitedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **lastCitedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **daysToFirstCitation** | **kotlin.Int** |  |  |
| **avgCitationPosition** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  |
| **models** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  |
| **brandMentioned** | **kotlin.Boolean** |  |  |


<a id="MatchType"></a>
## Enum: match_type
| Name | Value |
| ---- | ----- |
| matchType | url, prefix, domain |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | cited, lost, not_cited |



