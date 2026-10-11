
# TeamInvitation

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** | Kept by the member once they accept, when they move to GET /team_members. |  |
| **email** | **kotlin.String** |  |  |
| **permissionRole** | [**inline**](#PermissionRole) |  |  |
| **accountRole** | [**TeamAccountRole**](TeamAccountRole.md) |  |  |
| **permissions** | **kotlin.collections.Map&lt;kotlin.String, kotlin.collections.List&lt;kotlin.String&gt;&gt;** | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. |  |
| **accountAdmin** | **kotlin.Boolean** |  |  |
| **billingAccess** | **kotlin.Boolean** |  |  |
| **allProjects** | **kotlin.Boolean** |  |  |
| **projectIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** |  |  |
| **invitedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the invitation email was last sent. |  [optional] |
| **expiresAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the invitation link stops working. |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |


<a id="PermissionRole"></a>
## Enum: permission_role
| Name | Value |
| ---- | ----- |
| permissionRole | full_access, view_only, custom, account_role |



