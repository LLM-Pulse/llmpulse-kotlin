
# OwnedMediaProfile

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **url** | **kotlin.String** |  |  [optional] |
| **handle** | **kotlin.String** | The handle, page id, store app id, subreddit or username |  [optional] |
| **kind** | [**inline**](#Kind) |  |  [optional] |
| **main** | **kotlin.Boolean** | True for the main profile of its platform (or store), false for an extra one |  [optional] |
| **store** | **kotlin.String** | google_play or app_store for an app; null elsewhere |  [optional] |
| **name** | **kotlin.String** |  |  [optional] |
| **avatarUrl** | **kotlin.String** |  |  [optional] |
| **scrapeStatus** | **kotlin.String** | State of the profile scrape that reads its name and avatar: pending, running, ready, failed or skipped; null when none has started or the platform has none |  [optional] |


<a id="Kind"></a>
## Enum: kind
| Name | Value |
| ---- | ----- |
| kind | profile, app, subreddit, username |



