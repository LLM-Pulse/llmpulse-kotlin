
# OwnedMediaKpis

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **total** | **kotlin.Int** | Citations of the platform in the window, yours and everyone else&#39;s |  [optional] |
| **yours** | **kotlin.Int** | Citations of your own profiles and their content |  [optional] |
| **yourProfile** | **kotlin.Int** | Citations of your profile or channel pages. Null for mobile_apps and overview |  [optional] |
| **yourContent** | **kotlin.Int** | Citations of your posts or videos. Null for mobile_apps and overview |  [optional] |
| **sharePct** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | yours as a percentage of total (0-100) |  [optional] |
| **uniqueSubreddits** | **kotlin.Int** | Number of cited subreddits (provider&#x3D;reddit; null or omitted for other providers) |  [optional] |
| **uniqueAuthors** | **kotlin.Int** | Number of cited Reddit authors (provider&#x3D;reddit; null or omitted for other providers) |  [optional] |
| **positivePct** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Positive sentiment among rated Reddit citations, as a percentage (provider&#x3D;reddit; null or omitted for other providers) |  [optional] |



