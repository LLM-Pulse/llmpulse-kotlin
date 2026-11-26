
# RedditRow

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **subreddit** | **kotlin.String** | Subreddit name without the r/ prefix; null on a thread whose subreddit is unknown |  [optional] |
| **author** | **kotlin.String** | Reddit username; null on a thread whose author is unknown |  [optional] |
| **url** | **kotlin.String** | The subreddit, author profile or thread URL |  [optional] |
| **title** | **kotlin.String** | Thread title, read from the post or its URL (view&#x3D;threads) |  [optional] |
| **citations** | **kotlin.Int** | Reddit citations of the row in the window |  [optional] |
| **uniqueAuthors** | **kotlin.Int** | Distinct authors cited in the subreddit (view&#x3D;subreddits) |  [optional] |
| **positive** | **kotlin.Int** | Citations in answers with a positive or very positive sentiment |  [optional] |
| **negative** | **kotlin.Int** | Citations in answers with a negative or very negative sentiment |  [optional] |
| **neutral** | **kotlin.Int** | Citations in answers with a neutral sentiment |  [optional] |
| **positivePct** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | positive over the rated citations, 0-100; null when none is rated (view&#x3D;subreddits) |  [optional] |
| **negativePct** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | negative over the rated citations, 0-100; null when none is rated (view&#x3D;subreddits) |  [optional] |
| **yours** | **kotlin.Boolean** | Whether the account claims the subreddit or author as its own (on threads, either of them) |  [optional] |
| **subreddits** | **kotlin.collections.List&lt;kotlin.String&gt;** | The first subreddits the author was cited in (view&#x3D;authors) |  [optional] |
| **extraSubreddits** | **kotlin.Int** | Further subreddits the author was cited in, beyond those listed (view&#x3D;authors) |  [optional] |
| **leaning** | **kotlin.String** | positive, negative or neutral, whichever sentiment has more of the author&#39;s citations (view&#x3D;authors) |  [optional] |
| **brands** | [**kotlin.collections.List&lt;RedditAuthorBrand&gt;**](RedditAuthorBrand.md) | Brands the content of the author&#39;s cited posts names, your own first (view&#x3D;authors) |  [optional] |
| **subredditYours** | **kotlin.Boolean** | Whether the account claims the thread&#39;s subreddit (view&#x3D;threads) |  [optional] |
| **authorYours** | **kotlin.Boolean** | Whether the account claims the thread&#39;s author (view&#x3D;threads) |  [optional] |
| **latestCitedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | The thread&#39;s most recent citation (view&#x3D;threads) |  [optional] |
| **upvotes** | [**kotlin.Any**](.md) | Upvotes as the scraped post reports them, a number or a numeric string, or null when unknown (view&#x3D;threads) |  [optional] |
| **comments** | [**kotlin.Any**](.md) | Comment count as the scraped post reports it, a number or a numeric string, or null when unknown (view&#x3D;threads) |  [optional] |
| **avgPosition** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Average rank of the thread&#39;s citations, 1 &#x3D; first; null when no citation has a visible rank (view&#x3D;threads) |  [optional] |
| **sentiment** | **kotlin.String** | The most frequent sentiment of the answers that cite the thread; null when none is rated (view&#x3D;threads) |  [optional] |
| **archived** | [**kotlin.Any**](.md) | Whether the thread is archived as the scraped post reports it, usually a boolean, or null when unknown (view&#x3D;threads) |  [optional] |
| **postedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the thread was posted; null when unknown (view&#x3D;threads) |  [optional] |
| **breakdown** | **kotlin.String** | sentiment, model or country (view&#x3D;breakdowns) |  [optional] |
| **key** | **kotlin.String** | The slice, a sentiment label, a model or an uppercase country code (view&#x3D;breakdowns) |  [optional] |
| **count** | **kotlin.Int** | Reddit citations in the slice (view&#x3D;breakdowns) |  [optional] |
| **pct** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Share of the slice within its breakdown, 0-100 (view&#x3D;breakdowns) |  [optional] |



