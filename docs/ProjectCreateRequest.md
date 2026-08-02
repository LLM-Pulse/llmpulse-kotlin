
# ProjectCreateRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **websiteUrl** | [**java.net.URI**](java.net.URI.md) | Public HTTP(S) URL with a DNS hostname or public IP address. Credentials, private and special IP addresses, localhost and internal hostnames are rejected. |  |
| **name** | **kotlin.String** |  |  |
| **mainCountry** | **kotlin.String** |  |  |
| **mainLanguage** | **kotlin.String** |  |  |
| **brandName** | **kotlin.String** |  |  [optional] |
| **description** | **kotlin.String** |  |  [optional] |
| **industry** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **prompts** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **competitors** | [**kotlin.collections.List&lt;ProjectCreateRequestCompetitorsInner&gt;**](ProjectCreateRequestCompetitorsInner.md) |  |  [optional] |
| **ownedMedia** | [**ProjectCreateRequestOwnedMedia**](ProjectCreateRequestOwnedMedia.md) |  |  [optional] |
| **useSubdomain** | **kotlin.Boolean** |  |  [optional] |
| **weeklyEmailSubscribed** | **kotlin.Boolean** |  |  [optional] |
| **externalIdentifier** | **kotlin.String** | Embed-enabled (Enterprise) accounts only; other accounts receive ERR_PLAN_REQUIRED. Idempotency key and embed-session join key, unique per account |  [optional] |
| **executePromptsImmediately** | **kotlin.Boolean** |  |  [optional] |



