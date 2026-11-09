
# CmsPublication

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  [optional] |
| **platform** | [**inline**](#Platform) |  |  [optional] |
| **siteUrl** | **kotlin.String** |  |  [optional] |
| **status** | [**inline**](#Status) | queued and sending are on their way; unknown means a send timed out and the next attempt looks the draft up before creating one; drafted carries remote_id and edit_url; failed carries error_code |  [optional] |
| **title** | **kotlin.String** |  |  [optional] |
| **slug** | **kotlin.String** |  |  [optional] |
| **sourceUrl** | **kotlin.String** | For an update task, the page the draft revises |  [optional] |
| **remoteId** | **kotlin.Int** | WordPress post id of the draft |  [optional] |
| **remoteStatus** | **kotlin.String** | WordPress status of the post when the draft was created (draft) |  [optional] |
| **remoteUrl** | **kotlin.String** |  |  [optional] |
| **editUrl** | **kotlin.String** | The post&#39;s edit screen in the WordPress admin |  [optional] |
| **errorCode** | **kotlin.String** | Why the send failed, the same token as error.meta.reason, for example reconnect_required, authorization_header_lost, missing_capability, firewall_blocked, timeout, unreachable or rejected |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **sentAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |


<a id="Platform"></a>
## Enum: platform
| Name | Value |
| ---- | ----- |
| platform | wordpress |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | queued, sending, unknown, drafted, failed |



