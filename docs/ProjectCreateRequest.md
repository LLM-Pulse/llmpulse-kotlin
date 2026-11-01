
# ProjectCreateRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **websiteUrl** | [**java.net.URI**](java.net.URI.md) | Public HTTP(S) URL with a DNS hostname or public IP address. Credentials, private and special IP addresses, localhost and internal hostnames are rejected. |  |
| **name** | **kotlin.String** | Project name, as plain text. It can be changed later with PATCH /projects/{id} |  |
| **mainCountry** | **kotlin.String** |  |  |
| **mainLanguage** | **kotlin.String** |  |  |
| **brandName** | **kotlin.String** |  |  [optional] |
| **description** | **kotlin.String** |  |  [optional] |
| **industry** | **kotlin.collections.List&lt;kotlin.String&gt;** | Industry keys, case-insensitive; a single key string is also accepted. An unknown key returns ERR_INVALID_PARAM listing the valid keys (the same list as the in-app industry picker, e.g. TECHNOLOGY, SAAS, ECOMMERCE) |  [optional] |
| **businessModel** | **kotlin.String** | Business model key (e.g. B2B_SAAS, MARKETPLACE); unknown keys are rejected |  [optional] |
| **businessModelOther** | **kotlin.String** | Free-text business model, only accepted when business_model is OTHER; rejected against any other key |  [optional] |
| **targetAudience** | **kotlin.String** | Who the brand sells to. Context for Recommendations and GEO Writer (Brand Book) |  [optional] |
| **brandVoice** | **kotlin.String** | Tone of voice guidance for generated content (Brand Book) |  [optional] |
| **goals** | **kotlin.String** | What the brand wants to achieve. Context for GEO Writer and prompt suggestions |  [optional] |
| **primaryProducts** | **kotlin.collections.List&lt;kotlin.String&gt;** | Main products or services |  [optional] |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** | Brand-name variants used to detect mentions. At most 50 names of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) and nothing is created |  [optional] |
| **prompts** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **collections** | [**kotlin.collections.List&lt;ProjectCreateRequestCollectionsInner&gt;**](ProjectCreateRequestCollectionsInner.md) | Collections (prompt tags) created with the project, each tagging prompts of this request by their exact text, so no separate tagging calls are needed. A text that is not in prompts returns ERR_INVALID_PARAM. A team member also needs Tags: Create permission. |  [optional] |
| **competitors** | [**kotlin.collections.List&lt;ProjectCreateRequestCompetitorsInner&gt;**](ProjectCreateRequestCompetitorsInner.md) |  |  [optional] |
| **ownedMedia** | [**ProjectCreateRequestOwnedMedia**](ProjectCreateRequestOwnedMedia.md) |  |  [optional] |
| **useSubdomain** | **kotlin.Boolean** |  |  [optional] |
| **weeklyEmailSubscribed** | **kotlin.Boolean** |  |  [optional] |
| **externalIdentifier** | **kotlin.String** | Embed-enabled (Enterprise) accounts only; other accounts receive ERR_PLAN_REQUIRED. Idempotency key and embed-session join key, unique per account |  [optional] |
| **executePromptsImmediately** | **kotlin.Boolean** |  |  [optional] |
| **pitch** | **kotlin.Boolean** | Create a pitch project, a one-off snapshot for a prospect. It runs its prompts once across the account&#39;s AI models right away, takes no project slot and its prompts do not count against the prompt quota, and it is deleted 90 days later unless converted by sending pitch false to PATCH /projects/{id}. It uses one of the month&#39;s pitch projects (GET /account, limits.pitch_projects), needs access approved for the account and a paid subscription on the Scale tier or higher, takes 1 to 100 prompts, and cannot use a domain the account already tracks or pitched in the last 90 days. execute_prompts_immediately must not be false |  [optional] |



