
# UpdateCompetitorRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **brandName** | **kotlin.String** |  |  [optional] |
| **domain** | **kotlin.String** | Website domain or host used for citation matching. A full URL is accepted and normalised to its host. |  [optional] |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** | FULL replacement list of the names this competitor is matched by; brand_name is added automatically. At most 50 names in all, brand_name included, of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) and nothing in the request is applied |  [optional] |
| **color** | **kotlin.String** | Hex color, e.g. #1a2b3c |  [optional] |
| **citationMatchMode** | [**inline**](#CitationMatchMode) |  |  [optional] |
| **citationMatchPath** | **kotlin.String** | Required when changing citation_match_mode to path_prefix |  [optional] |


<a id="CitationMatchMode"></a>
## Enum: citation_match_mode
| Name | Value |
| ---- | ----- |
| citationMatchMode | domain, host, path_prefix |



