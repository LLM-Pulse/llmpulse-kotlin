
# CitationPageMentions

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **brandMentioned** | **kotlin.Boolean** |  |  |
| **competitorMentioned** | **kotlin.Boolean** |  |  |
| **brandPosition** | **kotlin.Int** | Rank of the brand&#39;s first mention on the page; null when it has none |  |
| **contentGapStatus** | **kotlin.String** | missing_page_cache, content_unavailable, mentions_not_processed, mentioned, gap (a competitor but not the brand) or not_mentioned |  |
| **brands** | [**kotlin.collections.List&lt;CitationPageMentionsBrandsInner&gt;**](CitationPageMentionsBrandsInner.md) | Each brand the page mentions once, in order of first mention |  |
| **mentions** | [**kotlin.collections.List&lt;CitationPageMentionsMentionsInner&gt;**](CitationPageMentionsMentionsInner.md) | Every mention on the page with its snippet; not sent on GET /citation_intelligence/groups |  [optional] |



