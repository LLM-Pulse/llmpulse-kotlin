
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
| **access** | [**inline**](#Access) | Whether the account may create pitch projects, which are for agency and platform accounts (the account type, which the account owner or an account admin changes in Account Settings &gt; Profile). none means the account is not an agency; approved access goes dormant while the account is below the Scale tier, on a trial, has a payment problem, is set to cancel or has an allowance of 0; revoked means our team turned it off. pending and rejected are no longer returned |  [optional] |


<a id="Access"></a>
## Enum: access
| Name | Value |
| ---- | ----- |
| access | none, pending, approved, dormant, rejected, revoked |



