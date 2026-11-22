
# ProjectDetailsAllOfBingWebmaster

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **status** | [**inline**](#Status) |  |  [optional] |
| **site** | **kotlin.String** | The connected site (e.g. https://example.com/), null when not connected |  [optional] |
| **lastSyncedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When that site last synced, null before its first sync |  [optional] |
| **connectUrl** | [**java.net.URI**](java.net.URI.md) | The in-app page where the site is connected or reconnected (Preferences &gt; Project Settings &gt; Connections) |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | connected, reconnect_required, not_connected |



