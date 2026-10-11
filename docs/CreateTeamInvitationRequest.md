
# CreateTeamInvitationRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **email** | **kotlin.String** |  |  |
| **projectIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** | Projects the member can access. Send this or all_projects true. |  [optional] |
| **allProjects** | **kotlin.Boolean** | Access to every project, including future ones |  [optional] |
| **permissionRole** | [**inline**](#PermissionRole) | Default full_access. Owner and co-owners only. |  [optional] |
| **accountRoleId** | **kotlin.Int** | One of the account&#39;s roles, with permission_role account_role |  [optional] |
| **permissions** | **kotlin.collections.Map&lt;kotlin.String, kotlin.collections.List&lt;kotlin.String&gt;&gt;** | With permission_role custom: feature key to the verbs granted (read, create, update, delete), for example {\&quot;overview\&quot;: [\&quot;read\&quot;], \&quot;prompts\&quot;: [\&quot;read\&quot;, \&quot;create\&quot;]} |  [optional] |
| **accountAdmin** | **kotlin.Boolean** | Make the member a co-owner. Account owner only. |  [optional] |
| **billingAccess** | **kotlin.Boolean** | Access to Billing and Plans. Account owner only. |  [optional] |


<a id="PermissionRole"></a>
## Enum: permission_role
| Name | Value |
| ---- | ----- |
| permissionRole | full_access, view_only, custom, account_role |



