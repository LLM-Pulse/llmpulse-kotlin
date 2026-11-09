
# OwnedMediaRow

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **date** | [**java.time.LocalDate**](java.time.LocalDate.md) | The start date of the actual reporting period (view&#x3D;activity) |  [optional] |
| **entityId** | **kotlin.String** | Platform entity identifier (view&#x3D;activity) |  [optional] |
| **entityName** | **kotlin.String** | Current entity name when known (view&#x3D;activity) |  [optional] |
| **entityUrl** | **kotlin.String** | Current profile, channel or app listing URL when known (view&#x3D;activity) |  [optional] |
| **store** | [**inline**](#Store) | Store selected for provider&#x3D;mobile_apps (view&#x3D;activity) |  [optional] |
| **competitorId** | **kotlin.Int** | Competitor identifier when the row represents a competitor&#39;s app or Trustpilot profile |  [optional] |
| **id** | **kotlin.Int** | The review&#39;s identifier (provider&#x3D;trustpilot, view&#x3D;reviews) |  [optional] |
| **brand** | **kotlin.String** | The brand or competitor whose Trustpilot profile carries the review (provider&#x3D;trustpilot, view&#x3D;reviews) |  [optional] |
| **rating** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Trustpilot rating out of 5: the profile&#39;s at its last monthly read (views profiles and brands) or the review&#39;s stars (view&#x3D;reviews) |  [optional] |
| **ratingChange** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Change of the profile&#39;s rating since the previous monthly read (provider&#x3D;trustpilot, view&#x3D;brands); null before a second read |  [optional] |
| **reviewsCount** | **kotlin.Int** | The profile&#39;s review count on Trustpilot at its last monthly read (provider&#x3D;trustpilot) |  [optional] |
| **status** | [**inline**](#Status) | Whether the brand&#39;s Trustpilot profile has been read (found), Trustpilot has no business for its domain (not_found), or it has not been read yet (pending) (provider&#x3D;trustpilot, view&#x3D;brands) |  [optional] |
| **text** | **kotlin.String** | The review text (provider&#x3D;trustpilot, view&#x3D;reviews) |  [optional] |
| **author** | **kotlin.String** | The reviewer&#39;s display name (provider&#x3D;trustpilot, view&#x3D;reviews) |  [optional] |
| **replied** | **kotlin.Boolean** | Whether the business replied to the review (provider&#x3D;trustpilot, view&#x3D;reviews) |  [optional] |
| **title** | **kotlin.String** |  |  [optional] |
| **url** | **kotlin.String** |  |  [optional] |
| **channelName** | **kotlin.String** |  |  [optional] |
| **channelHandle** | **kotlin.String** | The video&#39;s channel handle, without the @ |  [optional] |
| **channelUrl** | **kotlin.String** |  |  [optional] |
| **videoId** | **kotlin.String** |  |  [optional] |
| **key** | **kotlin.String** | The channel key (handle:..., channel:... or name:...), accepted as profile by /dimensions/owned_media/citing_prompts; on provider&#x3D;trustpilot, the business domain the profile is filed under, null for a brand without a domain |  [optional] |
| **name** | **kotlin.String** |  |  [optional] |
| **handle** | **kotlin.String** |  |  [optional] |
| **caption** | **kotlin.String** |  |  [optional] |
| **ownerHandle** | **kotlin.String** |  |  [optional] |
| **thumbnailUrl** | **kotlin.String** | The post or video image. Our cached copy where one exists, so the link does not expire |  [optional] |
| **avatarUrl** | **kotlin.String** | The profile or channel image. Our cached copy where one exists |  [optional] |
| **contentType** | **kotlin.String** | The post format on its platform: reel, post or tv on Instagram, post or pulse on LinkedIn, post elsewhere |  [optional] |
| **citations** | **kotlin.Int** | Citations for the row; for view&#x3D;activity, the count in this reporting period |  [optional] |
| **uniqueVideos** | **kotlin.Int** |  |  [optional] |
| **uniquePosts** | **kotlin.Int** |  |  [optional] |
| **followers** | **kotlin.Int** |  |  [optional] |
| **likes** | **kotlin.Int** |  |  [optional] |
| **comments** | **kotlin.Int** |  |  [optional] |
| **views** | [**kotlin.Any**](.md) | View count as the platform reports it, a number or a numeric string, or null when unknown |  [optional] |
| **publishedAt** | **kotlin.String** | Publication date as the platform reports it |  [optional] |
| **postedAt** | **kotlin.String** | Publication date as the platform reports it (ISO 8601, or Unix seconds on TikTok) |  [optional] |
| **avgPosition** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Average position of the citation in the answers (1 &#x3D; first); null when unknown |  [optional] |
| **yours** | **kotlin.Boolean** |  |  [optional] |
| **citationDate** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **position** | **kotlin.Int** |  |  [optional] |
| **model** | **kotlin.String** |  |  [optional] |
| **domain** | **kotlin.String** | The app&#39;s store listing URL (provider&#x3D;mobile_apps), or the brand&#39;s domain (provider&#x3D;trustpilot, view&#x3D;brands) |  [optional] |
| **totalResponses** | **kotlin.Int** |  |  [optional] |
| **rank** | **kotlin.Int** |  |  [optional] |
| **globalRank** | **kotlin.Int** |  |  [optional] |


<a id="Store"></a>
## Enum: store
| Name | Value |
| ---- | ----- |
| store | google_play, app_store |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | found, not_found, pending |



