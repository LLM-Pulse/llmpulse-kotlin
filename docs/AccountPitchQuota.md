
# AccountPitchQuota

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **limit** | **kotlin.Int** |  |  [optional] |
| **used** | **kotlin.Int** |  |  [optional] |
| **remaining** | **kotlin.Int** |  |  [optional] |
| **unlimited** | **kotlin.Boolean** |  |  [optional] |
| **period** | **kotlin.String** | Always month |  [optional] |
| **resetsOn** | [**java.time.LocalDate**](java.time.LocalDate.md) | The first day of next month, when the allowance starts again |  [optional] |
| **access** | [**inline**](#Access) | Whether the account may create pitch projects. The account owner or an account admin (co-owner) requests access in Account Settings &gt; Pitch projects and our team reviews it; approved access goes dormant while the account is below the Scale tier, on a trial, has a payment problem, is set to cancel or has an allowance of 0 |  [optional] |


<a id="Access"></a>
## Enum: access
| Name | Value |
| ---- | ----- |
| access | none, pending, approved, dormant, rejected, revoked |



