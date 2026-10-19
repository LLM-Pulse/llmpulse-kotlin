
# UpdateProjectDraftRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **step** | [**inline**](#Step) |  |  |
| **name** | **kotlin.String** |  |  [optional] |
| **brandName** | **kotlin.String** |  |  [optional] |
| **description** | **kotlin.String** |  |  [optional] |
| **industry** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** | Brand-name variants used to detect mentions (details step). At most 50 names of up to 100 characters each; the step stores the list as sent, and finalize refuses a longer list or name with ERR_INVALID_PARAM (422) |  [optional] |
| **externalIdentifier** | **kotlin.String** |  |  [optional] |
| **prompts** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **competitors** | [**kotlin.collections.List&lt;kotlin.Any&gt;**](kotlin.Any.md) | Competitors step: objects {domain, brand_name, matching_names}, capped by plan. Each competitor&#39;s matching_names takes at most 50 names of up to 100 characters, checked at finalize like POST /projects |  [optional] |
| **youtubeChannelUrl** | **kotlin.String** |  |  [optional] |
| **instagramProfileUrl** | **kotlin.String** |  |  [optional] |
| **facebookPageUrl** | **kotlin.String** |  |  [optional] |
| **tiktokProfileUrl** | **kotlin.String** |  |  [optional] |
| **appStoreUrl** | **kotlin.String** |  |  [optional] |
| **googlePlayUrl** | **kotlin.String** |  |  [optional] |
| **suggest** | **kotlin.Boolean** |  |  [optional] |


<a id="Step"></a>
## Enum: step
| Name | Value |
| ---- | ----- |
| step | details, prompts, competitors, owned_media |



