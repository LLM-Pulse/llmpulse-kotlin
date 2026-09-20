
# GetAccount200Response

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **plan** | **kotlin.String** | Plan key (starter, growth, scale, ...) |  [optional] |
| **trackingFrequency** | **kotlin.String** | How often prompts run (weekly, daily, monthly, ...) |  [optional] |
| **role** | [**inline**](#Role) | Whether the key belongs to the account owner or a team member |  [optional] |
| **subscription** | [**GetAccount200ResponseSubscription**](GetAccount200ResponseSubscription.md) |  |  [optional] |
| **limits** | [**GetAccount200ResponseLimits**](GetAccount200ResponseLimits.md) |  |  [optional] |
| **rateLimits** | [**GetAccount200ResponseRateLimits**](GetAccount200ResponseRateLimits.md) |  |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |


<a id="Role"></a>
## Enum: role
| Name | Value |
| ---- | ----- |
| role | owner, member |



