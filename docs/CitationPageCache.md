
# CitationPageCache

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **present** | **kotlin.Boolean** | Whether the page has a saved copy |  |
| **lastCrawledAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the saved copy was read; null without usable content |  |
| **statusCode** | **kotlin.Int** | A saved successful response or an observed 404/410; null otherwise |  |
| **errorMessage** | **kotlin.String** | Always null; crawl errors are not exposed |  |
| **contentFormat** | **kotlin.String** |  |  |
| **bytes** | **kotlin.Int** |  |  |
| **htmlTitle** | **kotlin.String** |  |  |
| **metaTitle** | **kotlin.String** |  |  |
| **metaDescription** | **kotlin.String** |  |  |
| **h1** | **kotlin.String** |  |  |
| **canonicalUrl** | **kotlin.String** |  |  |
| **language** | **kotlin.String** |  |  |
| **mentionsProcessed** | **kotlin.Boolean** | Whether the page&#39;s mention analysis has completed for this project |  |
| **contentAvailable** | **kotlin.Boolean** |  |  |



