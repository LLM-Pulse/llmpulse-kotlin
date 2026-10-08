
# AnswerDetails

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  [optional] |
| **promptId** | **kotlin.Int** |  |  [optional] |
| **promptText** | **kotlin.String** |  |  [optional] |
| **model** | **kotlin.String** |  |  [optional] |
| **response** | **kotlin.String** |  |  [optional] |
| **responseTruncated** | **kotlin.Boolean** |  |  [optional] |
| **executedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **durationMs** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Milliseconds, rounded to one decimal place |  [optional] |
| **success** | **kotlin.Boolean** | Null while the answer is still pending |  [optional] |
| **noResult** | **kotlin.Boolean** | True for a sentinel non-answer (the provider returned nothing after retries); excluded from platform metrics |  [optional] |
| **fanOutQueries** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **mentions** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) |  |  [optional] |
| **citations** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) |  |  [optional] |
| **competitorMentions** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) |  |  [optional] |
| **competitorCitations** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) |  |  [optional] |
| **sentiments** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) |  |  [optional] |
| **sources** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) |  |  [optional] |
| **shoppingProducts** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) |  |  [optional] |
| **brandEntities** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) |  |  [optional] |
| **localBusinesses** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) |  |  [optional] |
| **locale** | [**AnswerDetailsLocale**](AnswerDetailsLocale.md) |  |  [optional] |
| **appUrl** | [**java.net.URI**](java.net.URI.md) | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



