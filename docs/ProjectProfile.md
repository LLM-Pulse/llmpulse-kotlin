
# ProjectProfile

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **name** | **kotlin.String** |  |  |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  |
| **additionalOwnedDomains** | **kotlin.collections.List&lt;kotlin.String&gt;** | Other domains the brand owns (at most 10, each a website&#39;s own domain covering its subdomains), whose citations count as owned like the project website. Empty when none |  |
| **brandName** | **kotlin.String** |  |  [optional] |
| **description** | **kotlin.String** |  |  [optional] |
| **industry** | [**kotlin.Any**](.md) | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings. Deliberately untyped so generated clients decode either shape |  [optional] |
| **businessModel** | **kotlin.String** |  |  [optional] |
| **businessModelOther** | **kotlin.String** | Set only when business_model is OTHER |  [optional] |
| **targetAudience** | **kotlin.String** |  |  [optional] |
| **primaryProducts** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **brandVoice** | **kotlin.String** |  |  [optional] |
| **goals** | **kotlin.String** |  |  [optional] |



