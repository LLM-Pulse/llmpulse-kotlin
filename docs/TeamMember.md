
# TeamMember

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **email** | **kotlin.String** |  |  |
| **role** | [**inline**](#Role) | The account owner is listed first; everyone else who joined is a member. |  |
| **status** | [**inline**](#Status) | A blocked member cannot sign in or use the API until unblocked in the app. |  |
| **permissionRole** | **kotlin.String** | Access level of a member: full_access, view_only, custom or account_role. Null for the owner. |  |
| **accountRole** | [**TeamAccountRole**](TeamAccountRole.md) |  |  |
| **permissions** | **kotlin.collections.Map&lt;kotlin.String, kotlin.collections.List&lt;kotlin.String&gt;&gt;** | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. |  |
| **accountAdmin** | **kotlin.Boolean** | A co-owner, who can manage the team. |  |
| **billingAccess** | **kotlin.Boolean** | Can open Billing and Plans (always true for the owner). |  |
| **allProjects** | **kotlin.Boolean** | Has access to every project of the account, including future ones. |  |
| **projectIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** | The projects a member is limited to; empty when all_projects is true. |  |
| **name** | **kotlin.String** |  |  [optional] |
| **lastSignInAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **joinedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the member accepted the invitation; null for the owner and for members added without one. |  [optional] |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |


<a id="Role"></a>
## Enum: role
| Name | Value |
| ---- | ----- |
| role | owner, member |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | active, blocked |



