# ProjectsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createProject**](ProjectsApi.md#createProject) | **POST** /projects | Create a project (fast mode) |
| [**createProjectDraft**](ProjectsApi.md#createProjectDraft) | **POST** /project_drafts | Start a project draft (wizard step 1) |
| [**finalizeProjectDraft**](ProjectsApi.md#finalizeProjectDraft) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project |
| [**getProjectDraft**](ProjectsApi.md#getProjectDraft) | **GET** /project_drafts/{id} | Read a project draft |
| [**updateProjectDraft**](ProjectsApi.md#updateProjectDraft) | **PATCH** /project_drafts/{id} | Submit a wizard step |


<a id="createProject"></a>
# **createProject**
> ProjectCreateResponse createProject(projectCreateRequest)

Create a project (fast mode)

Create a complete project in one call: project fields, prompts (queued for execution and categorization), competitors, weekly email subscription. Idempotent via &#x60;external_identifier&#x60; (embed-enabled accounts only; replay returns 200 with the existing project). Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ProjectsApi()
val projectCreateRequest : ProjectCreateRequest =  // ProjectCreateRequest | 
try {
    val result : ProjectCreateResponse = apiInstance.createProject(projectCreateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ProjectsApi#createProject")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ProjectsApi#createProject")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectCreateRequest** | [**ProjectCreateRequest**](ProjectCreateRequest.md)|  | |

### Return type

[**ProjectCreateResponse**](ProjectCreateResponse.md)

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

<a id="createProjectDraft"></a>
# **createProjectDraft**
> createProjectDraft(createProjectDraftRequest)

Start a project draft (wizard step 1)

Start the multi-step project-creation wizard. Returns a draft_id plus AI suggestions (name, description, industry, brand aliases) for the URL. Cold URLs can take up to ~2 minutes to analyze; pass suggest&#x3D;false to skip AI and respond instantly. Drafts expire after 24h. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ProjectsApi()
val createProjectDraftRequest : CreateProjectDraftRequest =  // CreateProjectDraftRequest | 
try {
    apiInstance.createProjectDraft(createProjectDraftRequest)
} catch (e: ClientException) {
    println("4xx response calling ProjectsApi#createProjectDraft")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ProjectsApi#createProjectDraft")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createProjectDraftRequest** | [**CreateProjectDraftRequest**](CreateProjectDraftRequest.md)|  | |

### Return type

null (empty response body)

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

<a id="finalizeProjectDraft"></a>
# **finalizeProjectDraft**
> finalizeProjectDraft(id, finalizeProjectDraftRequest)

Finalize a draft into a real project

Creates the project with all accumulated draft data (same effects as POST /projects). Idempotent: finalizing an already-finalized draft returns 200 with the existing project. Optional overrides: weekly_email_subscribed, execute_prompts_immediately.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ProjectsApi()
val id : kotlin.String = id_example // kotlin.String | 
val finalizeProjectDraftRequest : FinalizeProjectDraftRequest =  // FinalizeProjectDraftRequest | 
try {
    apiInstance.finalizeProjectDraft(id, finalizeProjectDraftRequest)
} catch (e: ClientException) {
    println("4xx response calling ProjectsApi#finalizeProjectDraft")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ProjectsApi#finalizeProjectDraft")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **finalizeProjectDraftRequest** | [**FinalizeProjectDraftRequest**](FinalizeProjectDraftRequest.md)|  | [optional] |

### Return type

null (empty response body)

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

<a id="getProjectDraft"></a>
# **getProjectDraft**
> getProjectDraft(id, includeSuggestions)

Read a project draft

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ProjectsApi()
val id : kotlin.String = id_example // kotlin.String | Draft id (draft_...)
val includeSuggestions : kotlin.Boolean = true // kotlin.Boolean | Cache-only: returns suggestions for the current step if already generated, never triggers AI
try {
    apiInstance.getProjectDraft(id, includeSuggestions)
} catch (e: ClientException) {
    println("4xx response calling ProjectsApi#getProjectDraft")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ProjectsApi#getProjectDraft")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**| Draft id (draft_...) | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **includeSuggestions** | **kotlin.Boolean**| Cache-only: returns suggestions for the current step if already generated, never triggers AI | [optional] [default to false] |

### Return type

null (empty response body)

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

<a id="updateProjectDraft"></a>
# **updateProjectDraft**
> updateProjectDraft(id, updateProjectDraftRequest)

Submit a wizard step

Submit one step (details, prompts, competitors, owned_media). Strict forward gating: a step is only accepted when every previous step is complete (&#x60;ERR_DRAFT_STATE&#x60; otherwise); completed steps can be resubmitted. Responds with the updated draft plus AI suggestions for the next step.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ProjectsApi()
val id : kotlin.String = id_example // kotlin.String | 
val updateProjectDraftRequest : UpdateProjectDraftRequest =  // UpdateProjectDraftRequest | 
try {
    apiInstance.updateProjectDraft(id, updateProjectDraftRequest)
} catch (e: ClientException) {
    println("4xx response calling ProjectsApi#updateProjectDraft")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ProjectsApi#updateProjectDraft")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updateProjectDraftRequest** | [**UpdateProjectDraftRequest**](UpdateProjectDraftRequest.md)|  | |

### Return type

null (empty response body)

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

