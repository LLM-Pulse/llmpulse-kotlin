
# ProjectDetailsAllOfAgentTraffic

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **status** | [**inline**](#Status) |  |  [optional] |
| **provider** | **kotlin.String** | The connected source (e.g. cloudflare_graphql, bunny_cdn, s3 or the log drain&#39;s provider), null without a live source |  [optional] |
| **connectUrl** | [**java.net.URI**](java.net.URI.md) | The in-app Agent Analytics page, where a source is connected or reconnected |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | connected, reconnect_required, imported, not_connected |



