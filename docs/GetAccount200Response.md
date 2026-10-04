
# GetAccount200Response

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **plan** | **kotlin.String** | Plan key (starter, growth, scale, ...). Absent for a key limited to some projects. |  [optional] |
| **planName** | **kotlin.String** | Display name of the plan to show people (e.g. Scale++ for the scaleplusplus key). Absent for a key limited to some projects. |  [optional] |
| **trackingFrequency** | **kotlin.String** | How often prompts run (weekly, daily, monthly, ...) |  [optional] |
| **role** | [**inline**](#Role) | Whether the key belongs to the account owner or a team member |  [optional] |
| **apiKeyProjectIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** | The projects the calling API key is limited to; null for a key that sees the whole account, and for OAuth |  [optional] |
| **subscription** | [**GetAccount200ResponseSubscription**](GetAccount200ResponseSubscription.md) |  |  [optional] |
| **limits** | [**GetAccount200ResponseLimits**](GetAccount200ResponseLimits.md) |  |  [optional] |
| **rateLimits** | [**GetAccount200ResponseRateLimits**](GetAccount200ResponseRateLimits.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |


<a id="Role"></a>
## Enum: role
| Name | Value |
| ---- | ----- |
| role | owner, member |



