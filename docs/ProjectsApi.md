# ProjectsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createProject**](ProjectsApi.md#createProject) | **POST** /projects | Create a project (fast mode) |
| [**createProjectDraft**](ProjectsApi.md#createProjectDraft) | **POST** /project_drafts | Start a project draft (wizard step 1) |
| [**finalizeProjectDraft**](ProjectsApi.md#finalizeProjectDraft) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project |
| [**getProjectDetails**](ProjectsApi.md#getProjectDetails) | **GET** /dimensions/projects/{id} | Project details |
| [**getProjectDraft**](ProjectsApi.md#getProjectDraft) | **GET** /project_drafts/{id} | Read a project draft |
| [**listLocales**](ProjectsApi.md#listLocales) | **GET** /dimensions/locales | List locales with data |
| [**listModels**](ProjectsApi.md#listModels) | **GET** /dimensions/models | List models with data |
| [**listProjects**](ProjectsApi.md#listProjects) | **GET** /dimensions/projects | List projects |
| [**updateProject**](ProjectsApi.md#updateProject) | **PATCH** /projects/{id} | Update a project profile (Brand Book) |
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

<a id="getProjectDetails"></a>
# **getProjectDetails**
> ProjectDetails getProjectDetails(id)

Project details

Detailed info for one project: matching_names, industry, business model, primary products, target audience, brand voice, locale, app store IDs, stats (incl. prompts_by_brand_kind counts) and data_coverage (models, countries and languages with data).

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ProjectsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
try {
    val result : ProjectDetails = apiInstance.getProjectDetails(id)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ProjectsApi#getProjectDetails")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ProjectsApi#getProjectDetails")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int**|  | |

### Return type

[**ProjectDetails**](ProjectDetails.md)

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

<a id="listLocales"></a>
# **listLocales**
> listLocales(projectId)

List locales with data

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ProjectsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.listLocales(projectId)
} catch (e: ClientException) {
    println("4xx response calling ProjectsApi#listLocales")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ProjectsApi#listLocales")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

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
 - **Accept**: Not defined

<a id="listModels"></a>
# **listModels**
> listModels(projectId)

List models with data

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ProjectsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.listModels(projectId)
} catch (e: ClientException) {
    println("4xx response calling ProjectsApi#listModels")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ProjectsApi#listModels")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

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
 - **Accept**: Not defined

<a id="listProjects"></a>
# **listProjects**
> ListProjects200Response listProjects(output)

List projects

All projects accessible with your API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ProjectsApi()
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : ListProjects200Response = apiInstance.listProjects(output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ProjectsApi#listProjects")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ProjectsApi#listProjects")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**ListProjects200Response**](ListProjects200Response.md)

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

<a id="updateProject"></a>
# **updateProject**
> updateProject(id, updateProjectRequest)

Update a project profile (Brand Book)

Updates the project profile, the same fields as Project Settings: brand_name, description, industry, business_model (plus business_model_other when it is OTHER), target_audience, brand_voice, goals, primary_products, matching_names. Send only the fields to change; unknown fields are rejected. All seven Brand Book fields feed every GEO Writer task and prompt suggestions; only industry, description, and target_audience help Recommendations. A matching_names change re-runs mention/citation matching over the project history in the background (rematching&#x3D;true); further edits are rejected while that runs. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ProjectsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val updateProjectRequest : UpdateProjectRequest =  // UpdateProjectRequest | 
try {
    apiInstance.updateProject(id, updateProjectRequest)
} catch (e: ClientException) {
    println("4xx response calling ProjectsApi#updateProject")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ProjectsApi#updateProject")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updateProjectRequest** | [**UpdateProjectRequest**](UpdateProjectRequest.md)|  | |

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

