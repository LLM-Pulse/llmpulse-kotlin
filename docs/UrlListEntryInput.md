
# UrlListEntryInput

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **&#x60;value&#x60;** | **kotlin.String** | An exact URL, a \&quot;host/path/_*\&quot; prefix or a domain. |  |
| **matchType** | [**inline**](#MatchType) |  |  [optional] |
| **addedOn** | [**java.time.LocalDate**](java.time.LocalDate.md) | When the URL was published or bought. Default today. |  [optional] |
| **cost** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | What the URL cost, in the list currency. |  [optional] |
| **channel** | **kotlin.String** | Where it came from, such as a marketplace or PR agency. |  [optional] |


<a id="MatchType"></a>
## Enum: match_type
| Name | Value |
| ---- | ----- |
| matchType | url, prefix, domain |



