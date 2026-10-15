
# OwnedMediaRow

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **title** | **kotlin.String** |  |  [optional] |
| **url** | **kotlin.String** |  |  [optional] |
| **channelName** | **kotlin.String** |  |  [optional] |
| **channelHandle** | **kotlin.String** | The video&#39;s channel handle, without the @ |  [optional] |
| **channelUrl** | **kotlin.String** |  |  [optional] |
| **videoId** | **kotlin.String** |  |  [optional] |
| **key** | **kotlin.String** | The channel key (handle:..., channel:... or name:...), accepted as profile by /dimensions/owned_media/citing_prompts |  [optional] |
| **name** | **kotlin.String** |  |  [optional] |
| **handle** | **kotlin.String** |  |  [optional] |
| **caption** | **kotlin.String** |  |  [optional] |
| **ownerHandle** | **kotlin.String** |  |  [optional] |
| **thumbnailUrl** | **kotlin.String** | The post or video image. Our cached copy where one exists, so the link does not expire |  [optional] |
| **avatarUrl** | **kotlin.String** | The profile or channel image. Our cached copy where one exists |  [optional] |
| **contentType** | **kotlin.String** | The post format on its platform: reel, post or tv on Instagram, post or pulse on LinkedIn, post elsewhere |  [optional] |
| **citations** | **kotlin.Int** |  |  [optional] |
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
| **domain** | **kotlin.String** | The app&#39;s store listing URL (provider&#x3D;mobile_apps) |  [optional] |
| **totalResponses** | **kotlin.Int** |  |  [optional] |
| **rank** | **kotlin.Int** |  |  [optional] |
| **globalRank** | **kotlin.Int** |  |  [optional] |



