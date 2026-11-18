
# UrlListCreateRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **name** | **kotlin.String** |  |  |
| **description** | **kotlin.String** |  |  [optional] |
| **currency** | [**inline**](#Currency) |  |  [optional] |
| **propertyEntries** | [**kotlin.collections.List&lt;UrlListEntryInput&gt;**](UrlListEntryInput.md) |  |  [optional] |
| **matchType** | [**inline**](#MatchType) | Read every entry without its own match_type as this type. Default detects it from each value. |  [optional] |


<a id="Currency"></a>
## Enum: currency
| Name | Value |
| ---- | ----- |
| currency | USD, EUR, GBP |


<a id="MatchType"></a>
## Enum: match_type
| Name | Value |
| ---- | ----- |
| matchType | url, prefix, domain |



