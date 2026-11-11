
# OwnedMediaSummaryResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **provider** | **kotlin.String** |  |  [optional] |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **connected** | **kotlin.Boolean** | Whether a profile is claimed on the platform (on overview, on any platform) |  [optional] |
| **kpis** | [**OwnedMediaKpis**](OwnedMediaKpis.md) |  |  [optional] |
| **previous** | [**OwnedMediaSummaryResponsePrevious**](OwnedMediaSummaryResponsePrevious.md) |  |  [optional] |
| **changes** | [**OwnedMediaKpiChanges**](OwnedMediaKpiChanges.md) |  |  [optional] |
| **weekly** | [**kotlin.collections.List&lt;OwnedMediaWeek&gt;**](OwnedMediaWeek.md) |  |  [optional] |
| **byModel** | [**kotlin.collections.List&lt;OwnedMediaModelShare&gt;**](OwnedMediaModelShare.md) | Null for provider&#x3D;overview |  [optional] |
| **byCountry** | [**kotlin.collections.List&lt;OwnedMediaCountryShare&gt;**](OwnedMediaCountryShare.md) | Null for provider&#x3D;overview |  [optional] |
| **contentTypes** | [**kotlin.collections.List&lt;OwnedMediaContentTypeShare&gt;**](OwnedMediaContentTypeShare.md) | Social and YouTube providers only |  [optional] |
| **ageBuckets** | [**kotlin.collections.List&lt;OwnedMediaAgeBucketShare&gt;**](OwnedMediaAgeBucketShare.md) | Social and YouTube providers only. Posts or videos without a known publication date are left out |  [optional] |
| **stores** | [**kotlin.collections.List&lt;OwnedMediaStoreTotals&gt;**](OwnedMediaStoreTotals.md) | provider&#x3D;mobile_apps only |  [optional] |
| **platforms** | [**kotlin.collections.List&lt;OwnedMediaPlatformRollup&gt;**](OwnedMediaPlatformRollup.md) | provider&#x3D;overview only, one row per platform the caller can read |  [optional] |
| **activity** | [**kotlin.collections.List&lt;OwnedMediaSummaryActivityPeriod&gt;**](OwnedMediaSummaryActivityPeriod.md) | All providers. One row per actual project reporting period with runs; provider&#x3D;overview has null yours and other, and provider&#x3D;reddit also returns positive, neutral and negative sentiment counts. Citation counts use the selected date window, and periods with runs but no citation have zero |  [optional] |
| **subredditActivity** | [**kotlin.collections.List&lt;RedditSubredditActivityPeriod&gt;**](RedditSubredditActivityPeriod.md) | provider&#x3D;reddit only. One row per subreddit and actual reporting period; the top five subreddits are separate and Others has a null subreddit |  [optional] |
| **positions** | [**kotlin.collections.List&lt;RedditPositionShare&gt;**](RedditPositionShare.md) | provider&#x3D;reddit only. Position distribution over the selected date window |  [optional] |
| **brandShare** | [**kotlin.collections.List&lt;RedditBrandShare&gt;**](RedditBrandShare.md) | provider&#x3D;reddit only. Citation share among the tracked brand and competitors with cited mentions |  [optional] |
| **replies** | [**TrustpilotReplies**](TrustpilotReplies.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



