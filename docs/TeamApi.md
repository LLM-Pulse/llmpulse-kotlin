# TeamApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createTeamInvitation**](TeamApi.md#createTeamInvitation) | **POST** /team_invitations | Invite a team member |
| [**listTeamInvitations**](TeamApi.md#listTeamInvitations) | **GET** /team_invitations | List pending team invitations |
| [**listTeamMembers**](TeamApi.md#listTeamMembers) | **GET** /team_members | List team members |
| [**removeTeamMember**](TeamApi.md#removeTeamMember) | **DELETE** /team_members/{id} | Remove a team member |
| [**revokeTeamInvitation**](TeamApi.md#revokeTeamInvitation) | **DELETE** /team_invitations/{id} | Revoke a pending team invitation |


<a id="createTeamInvitation"></a>
# **createTeamInvitation**
> CreateTeamInvitation201Response createTeamInvitation(createTeamInvitationRequest)

Invite a team member

Invites someone to the account team with the same rules as the Team Members settings page, and sends them the invitation email (email_sent is false when the email provider refused it; the invitation still exists, so revoke it and invite again once the address is fixed). Send project_ids, or all_projects: true for every project (for a team member inviting, every project they can access). The account owner and co-owners choose the access with permission_role: full_access (default), view_only, custom (with permissions, feature key to verbs) or account_role (with account_role_id). A team member with permission to invite cannot choose access: leave those fields out and the invitation copies their own permissions. Only the account owner can set account_admin (co-owner) or billing_access. An address already registered on the platform, or with an invitation pending, is refused with ERR_INVALID_PARAM (revoke the pending one first). An account that cannot add more team members, or that reached its daily limit of invitations sent through the API and MCP (revoked ones count), answers ERR_LIMIT_REACHED; the message says which. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = TeamApi()
val createTeamInvitationRequest : CreateTeamInvitationRequest =  // CreateTeamInvitationRequest | 
try {
    val result : CreateTeamInvitation201Response = apiInstance.createTeamInvitation(createTeamInvitationRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling TeamApi#createTeamInvitation")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling TeamApi#createTeamInvitation")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createTeamInvitationRequest** | [**CreateTeamInvitationRequest**](CreateTeamInvitationRequest.md)|  | |

### Return type

[**CreateTeamInvitation201Response**](CreateTeamInvitation201Response.md)

### Authorization


Configure BearerAuth statically:
```kotlin
ApiClient.accessToken = ""
```
Configure BearerAuth dynamically:
```kotlin
apiInstance.accessTokenProvider = { "" }
```

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

<a id="listTeamInvitations"></a>
# **listTeamInvitations**
> ListTeamInvitations200Response listTeamInvitations(page, perPage)

List pending team invitations

Lists invitations that have not been accepted yet: the address, the access and projects the person will get, when the invitation was sent and when its link expires. An accepted invitation keeps its id and moves to GET /team_members. Same access rules as GET /team_members.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = TeamApi()
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | Default 20, max 100
try {
    val result : ListTeamInvitations200Response = apiInstance.listTeamInvitations(page, perPage)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling TeamApi#listTeamInvitations")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling TeamApi#listTeamInvitations")
    e.printStackTrace()
}
```

### Parameters
| **page** | **kotlin.Int**|  | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**| Default 20, max 100 | [optional] |

### Return type

[**ListTeamInvitations200Response**](ListTeamInvitations200Response.md)

### Authorization


Configure BearerAuth statically:
```kotlin
ApiClient.accessToken = ""
```
Configure BearerAuth dynamically:
```kotlin
apiInstance.accessTokenProvider = { "" }
```

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="listTeamMembers"></a>
# **listTeamMembers**
> ListTeamMembers200Response listTeamMembers(page, perPage)

List team members

Lists the account owner first, then every team member who joined, with their access level (permission_role, account role and the resulting permissions), co-owner and billing flags, project access, status (active or blocked) and last sign-in. Pending invitations are listed by GET /team_invitations; GET /account limits.team_members.used counts both. Available to the account owner, co-owners and team members with the Team Members permission. A key limited to some projects answers ERR_KEY_PROJECT_SCOPED: the team belongs to the whole account.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = TeamApi()
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | Default 20, max 100
try {
    val result : ListTeamMembers200Response = apiInstance.listTeamMembers(page, perPage)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling TeamApi#listTeamMembers")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling TeamApi#listTeamMembers")
    e.printStackTrace()
}
```

### Parameters
| **page** | **kotlin.Int**|  | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**| Default 20, max 100 | [optional] |

### Return type

[**ListTeamMembers200Response**](ListTeamMembers200Response.md)

### Authorization


Configure BearerAuth statically:
```kotlin
ApiClient.accessToken = ""
```
Configure BearerAuth dynamically:
```kotlin
apiInstance.accessTokenProvider = { "" }
```

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="removeTeamMember"></a>
# **removeTeamMember**
> RemoveTeamMember200Response removeTeamMember(id)

Remove a team member

Removes a member from the team, as the settings page does: their sessions and API keys stop working at once and their user account is deleted in the background shortly after. Account owner or co-owner only; a co-owner cannot remove the owner, another co-owner or themselves. The owner cannot be removed. Pending invitations are revoked with DELETE /team_invitations/{id}; an id that is not a member of the account answers ERR_NOT_FOUND. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = TeamApi()
val id : kotlin.Int = 56 // kotlin.Int | The member id from GET /team_members
try {
    val result : RemoveTeamMember200Response = apiInstance.removeTeamMember(id)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling TeamApi#removeTeamMember")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling TeamApi#removeTeamMember")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int**| The member id from GET /team_members | |

### Return type

[**RemoveTeamMember200Response**](RemoveTeamMember200Response.md)

### Authorization


Configure BearerAuth statically:
```kotlin
ApiClient.accessToken = ""
```
Configure BearerAuth dynamically:
```kotlin
apiInstance.accessTokenProvider = { "" }
```

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="revokeTeamInvitation"></a>
# **revokeTeamInvitation**
> RevokeTeamInvitation200Response revokeTeamInvitation(id)

Revoke a pending team invitation

Revokes a pending invitation: its link stops working immediately. Account owner or co-owner only, and a co-owner cannot revoke an invitation that makes someone a co-owner. Members who already joined are removed with DELETE /team_members/{id}; an id that is not a pending invitation of the account answers ERR_NOT_FOUND. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = TeamApi()
val id : kotlin.Int = 56 // kotlin.Int | The invitation id from GET /team_invitations
try {
    val result : RevokeTeamInvitation200Response = apiInstance.revokeTeamInvitation(id)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling TeamApi#revokeTeamInvitation")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling TeamApi#revokeTeamInvitation")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int**| The invitation id from GET /team_invitations | |

### Return type

[**RevokeTeamInvitation200Response**](RevokeTeamInvitation200Response.md)

### Authorization


Configure BearerAuth statically:
```kotlin
ApiClient.accessToken = ""
```
Configure BearerAuth dynamically:
```kotlin
apiInstance.accessTokenProvider = { "" }
```

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

