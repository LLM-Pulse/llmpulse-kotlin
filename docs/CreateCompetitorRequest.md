
# CreateCompetitorRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **brandName** | **kotlin.String** |  |  |
| **domain** | **kotlin.String** | URL is accepted and normalised to host (e.g. https://www.openai.com → openai.com) |  |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** | Extra names this competitor is matched by; brand_name is added automatically. At most 50 names in all, brand_name included, of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) |  [optional] |
| **citationMatchMode** | [**inline**](#CitationMatchMode) | domain includes the registrable domain and all subdomains; host requires the exact hostname; path_prefix also requires citation_match_path |  [optional] |
| **citationMatchPath** | **kotlin.String** | Required when citation_match_mode&#x3D;path_prefix, e.g. /es. Case-sensitive; trailing slash is optional; query and fragment are ignored |  [optional] |


<a id="CitationMatchMode"></a>
## Enum: citation_match_mode
| Name | Value |
| ---- | ----- |
| citationMatchMode | domain, host, path_prefix |



