
# CreateTechnicalGeoReportsRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **url** | **kotlin.String** |  |  |
| **countryCode** | **kotlin.String** | Defaults to the project country |  [optional] |
| **outputLanguageCode** | **kotlin.String** | ISO 639-1 code of the language the llms.txt files are written in (for example es). Defaults to the project language, else en. Only the llms.txt report of the bundle uses it; an unsupported code returns 422 ERR_INVALID_PARAM |  [optional] |



