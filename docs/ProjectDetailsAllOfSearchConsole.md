
# ProjectDetailsAllOfSearchConsole

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **status** | [**inline**](#Status) |  |  [optional] |
| **&#x60;property&#x60;** | **kotlin.String** | The primary property (e.g. sc-domain:example.com), null when not connected |  [optional] |
| **connectUrl** | [**java.net.URI**](java.net.URI.md) | The in-app page where the property is connected or reconnected (Preferences &gt; Project Settings &gt; Data Connections) |  [optional] |
| **propertiesCount** | **kotlin.Int** | Connected properties Google still accepts (reconnect_required ones excluded); GET /search_console/properties lists every property with its status |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | connected, reconnect_required, not_connected |



