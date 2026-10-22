
# ProjectDetailsAllOfAiTraffic

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **status** | [**inline**](#Status) |  |  [optional] |
| **provider** | **kotlin.String** | The connected provider (e.g. google_analytics, adobe_analytics, adobe_cja, posthog, plausible, matomo, piano), null when not connected |  [optional] |
| **connectUrl** | [**java.net.URI**](java.net.URI.md) | The in-app AI Traffic page, where the provider is connected or reconnected |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | connected, reconnect_required, not_connected |



