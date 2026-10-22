
# PromptGenerationRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **source** | [**inline**](#Source) | Which Add prompts generator to run |  |
| **query** | **kotlin.String** | keyword: optional keyword or research query. topic and reddit: required topic (reddit: the brand when search_type&#x3D;brand). paa: one keyword, as an alternative to keywords. |  [optional] |
| **count** | **kotlin.Int** | keyword and topic: how many suggestions to ask for, capped by the prompt slots left |  [optional] |
| **countryCode** | **kotlin.String** | ISO 3166-1 alpha-2 country of the suggestions (default the project country) |  [optional] |
| **languageCode** | **kotlin.String** | ISO language code of the suggestions (default the project language) |  [optional] |
| **competitorId** | **kotlin.Int** | keyword: write the suggestions around this competitor of the project |  [optional] |
| **searchType** | [**inline**](#SearchType) | reddit: search discussions of a topic or a brand |  [optional] |
| **keywords** | **kotlin.collections.List&lt;kotlin.String&gt;** | paa: up to 5 keywords; each is a People Also Ask lookup counted against the account&#39;s 24-hour allowance |  [optional] |
| **sourceCountryCode** | **kotlin.String** | translate: country of the prompts to translate |  [optional] |
| **sourceLanguageCode** | **kotlin.String** | translate: language of the prompts to translate |  [optional] |
| **minWords** | **kotlin.Int** | search_console: skip queries shorter than this many words |  [optional] |
| **allCountries** | **kotlin.Boolean** | search_console: include queries from every country instead of country_code only |  [optional] |
| **&#x60;property&#x60;** | **kotlin.String** | search_console: the property id to read queries from (GET /search_console/properties lists them); the primary property when omitted |  [optional] |


<a id="Source"></a>
## Enum: source
| Name | Value |
| ---- | ----- |
| source | website, keyword, topic, reddit, paa, reputational, translate, search_console |


<a id="SearchType"></a>
## Enum: search_type
| Name | Value |
| ---- | ----- |
| searchType | topic, brand |



