
# CreateCompetitorRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **brandName** | **kotlin.String** |  |  |
| **domain** | **kotlin.String** | URL is accepted and normalised to host (e.g. https://www.openai.com → openai.com) |  |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **citationMatchMode** | [**inline**](#CitationMatchMode) | domain includes the registrable domain and all subdomains; host requires the exact hostname; path_prefix also requires citation_match_path |  [optional] |
| **citationMatchPath** | **kotlin.String** | Required when citation_match_mode&#x3D;path_prefix, e.g. /es. Case-sensitive; trailing slash is optional; query and fragment are ignored |  [optional] |


<a id="CitationMatchMode"></a>
## Enum: citation_match_mode
| Name | Value |
| ---- | ----- |
| citationMatchMode | domain, host, path_prefix |



