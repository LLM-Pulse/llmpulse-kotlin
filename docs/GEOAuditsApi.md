# GEOAuditsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**compareGeoAuditRuns**](GEOAuditsApi.md#compareGeoAuditRuns) | **GET** /geo_audits/{id}/comparison | Compare two GEO audit runs |
| [**createGeoAudits**](GEOAuditsApi.md#createGeoAudits) | **POST** /geo_audits | Create GEO audits |
| [**deleteGeoAudit**](GEOAuditsApi.md#deleteGeoAudit) | **DELETE** /geo_audits/{id} | Delete (archive) a GEO audit |
| [**getGeoAudit**](GEOAuditsApi.md#getGeoAudit) | **GET** /geo_audits/{id} | Get a GEO audit |
| [**getGeoAuditRun**](GEOAuditsApi.md#getGeoAuditRun) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence} | Get a GEO audit run |
| [**listGeoAlerts**](GEOAuditsApi.md#listGeoAlerts) | **GET** /geo_alerts | List GEO audit alerts |
| [**listGeoAuditFindings**](GEOAuditsApi.md#listGeoAuditFindings) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence}/findings | List the findings of a GEO audit run |
| [**listGeoAuditIssues**](GEOAuditsApi.md#listGeoAuditIssues) | **GET** /geo_audits/{geo_audit_id}/issues | List the issues of a GEO audit |
| [**listGeoAuditRuns**](GEOAuditsApi.md#listGeoAuditRuns) | **GET** /geo_audits/{geo_audit_id}/runs | List the runs of a GEO audit |
| [**listGeoAudits**](GEOAuditsApi.md#listGeoAudits) | **GET** /geo_audits | List GEO audits |
| [**runGeoAudit**](GEOAuditsApi.md#runGeoAudit) | **POST** /geo_audits/{geo_audit_id}/runs | Run a GEO audit now |
| [**updateGeoAudit**](GEOAuditsApi.md#updateGeoAudit) | **PATCH** /geo_audits/{id} | Update a GEO audit |
| [**updateGeoAuditIssue**](GEOAuditsApi.md#updateGeoAuditIssue) | **PATCH** /geo_audits/{geo_audit_id}/issues/{id} | Accept or reopen a GEO audit issue |


<a id="compareGeoAuditRuns"></a>
# **compareGeoAuditRuns**
> GeoAuditComparison compareGeoAuditRuns(id, projectId, fromRun, toRun)

Compare two GEO audit runs

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val id : kotlin.String = id_example // kotlin.String | Audit id
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val fromRun : kotlin.Int = 56 // kotlin.Int | Run number to compare from (default the run before to_run)
val toRun : kotlin.Int = 56 // kotlin.Int | Run number to compare to (default the latest completed run)
try {
    val result : GeoAuditComparison = apiInstance.compareGeoAuditRuns(id, projectId, fromRun, toRun)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#compareGeoAuditRuns")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#compareGeoAuditRuns")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**| Audit id | |
| **projectId** | **kotlin.Int**| Project ID | |
| **fromRun** | **kotlin.Int**| Run number to compare from (default the run before to_run) | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **toRun** | **kotlin.Int**| Run number to compare to (default the latest completed run) | [optional] |

### Return type

[**GeoAuditComparison**](GeoAuditComparison.md)

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

<a id="createGeoAudits"></a>
# **createGeoAudits**
> GeoAuditCreateResponse createGeoAudits(geoAuditCreateRequest)

Create GEO audits

Creates one audit per entry of audit_types and starts the first run of each (it counts against the manual run limits: 6 per audit per hour, 200 per account per day). cadence weekly or monthly is accepted only for types whose checks are tracked run to run, and counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Creating an audit that was archived restores it with its history. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val geoAuditCreateRequest : GeoAuditCreateRequest =  // GeoAuditCreateRequest | 
try {
    val result : GeoAuditCreateResponse = apiInstance.createGeoAudits(geoAuditCreateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#createGeoAudits")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#createGeoAudits")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **geoAuditCreateRequest** | [**GeoAuditCreateRequest**](GeoAuditCreateRequest.md)|  | |

### Return type

[**GeoAuditCreateResponse**](GeoAuditCreateResponse.md)

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

<a id="deleteGeoAudit"></a>
# **deleteGeoAudit**
> GeoAuditArchived deleteGeoAudit(id, projectId)

Delete (archive) a GEO audit

Archives the audit. Requires a &#x60;read_write&#x60; scope API key and, for team members, delete permission on GEO Optimization.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val id : kotlin.String = id_example // kotlin.String | Audit id
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    val result : GeoAuditArchived = apiInstance.deleteGeoAudit(id, projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#deleteGeoAudit")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#deleteGeoAudit")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**| Audit id | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

### Return type

[**GeoAuditArchived**](GeoAuditArchived.md)

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

<a id="getGeoAudit"></a>
# **getGeoAudit**
> GeoAuditResponse getGeoAudit(id, projectId)

Get a GEO audit

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val id : kotlin.String = id_example // kotlin.String | Audit id
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    val result : GeoAuditResponse = apiInstance.getGeoAudit(id, projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#getGeoAudit")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#getGeoAudit")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**| Audit id | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

### Return type

[**GeoAuditResponse**](GeoAuditResponse.md)

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

<a id="getGeoAuditRun"></a>
# **getGeoAuditRun**
> GeoAuditRunDetail getGeoAuditRun(geoAuditId, sequence, projectId)

Get a GEO audit run

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val geoAuditId : kotlin.String = geoAuditId_example // kotlin.String | Audit id
val sequence : kotlin.Int = 56 // kotlin.Int | Run number within the audit
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    val result : GeoAuditRunDetail = apiInstance.getGeoAuditRun(geoAuditId, sequence, projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#getGeoAuditRun")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#getGeoAuditRun")
    e.printStackTrace()
}
```

### Parameters
| **geoAuditId** | **kotlin.String**| Audit id | |
| **sequence** | **kotlin.Int**| Run number within the audit | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

### Return type

[**GeoAuditRunDetail**](GeoAuditRunDetail.md)

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

<a id="listGeoAlerts"></a>
# **listGeoAlerts**
> GeoAlertList listGeoAlerts(projectId, auditId, page, perPage)

List GEO audit alerts

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val auditId : kotlin.String = auditId_example // kotlin.String | Only alerts of this audit
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    val result : GeoAlertList = apiInstance.listGeoAlerts(projectId, auditId, page, perPage)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#listGeoAlerts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#listGeoAlerts")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **auditId** | **kotlin.String**| Only alerts of this audit | [optional] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |

### Return type

[**GeoAlertList**](GeoAlertList.md)

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

<a id="listGeoAuditFindings"></a>
# **listGeoAuditFindings**
> GeoAuditFindingList listGeoAuditFindings(geoAuditId, sequence, projectId, page, perPage, output)

List the findings of a GEO audit run

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val geoAuditId : kotlin.String = geoAuditId_example // kotlin.String | Audit id
val sequence : kotlin.Int = 56 // kotlin.Int | Run number within the audit
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : GeoAuditFindingList = apiInstance.listGeoAuditFindings(geoAuditId, sequence, projectId, page, perPage, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#listGeoAuditFindings")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#listGeoAuditFindings")
    e.printStackTrace()
}
```

### Parameters
| **geoAuditId** | **kotlin.String**| Audit id | |
| **sequence** | **kotlin.Int**| Run number within the audit | |
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**GeoAuditFindingList**](GeoAuditFindingList.md)

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

<a id="listGeoAuditIssues"></a>
# **listGeoAuditIssues**
> GeoAuditIssueList listGeoAuditIssues(geoAuditId, projectId, state, page, perPage)

List the issues of a GEO audit

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val geoAuditId : kotlin.String = geoAuditId_example // kotlin.String | Audit id
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val state : kotlin.String = state_example // kotlin.String | open means open and not accepted; default all
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    val result : GeoAuditIssueList = apiInstance.listGeoAuditIssues(geoAuditId, projectId, state, page, perPage)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#listGeoAuditIssues")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#listGeoAuditIssues")
    e.printStackTrace()
}
```

### Parameters
| **geoAuditId** | **kotlin.String**| Audit id | |
| **projectId** | **kotlin.Int**| Project ID | |
| **state** | **kotlin.String**| open means open and not accepted; default all | [optional] [enum: open, accepted, fixed, gone] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |

### Return type

[**GeoAuditIssueList**](GeoAuditIssueList.md)

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

<a id="listGeoAuditRuns"></a>
# **listGeoAuditRuns**
> GeoAuditRunList listGeoAuditRuns(geoAuditId, projectId, page, perPage, output)

List the runs of a GEO audit

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val geoAuditId : kotlin.String = geoAuditId_example // kotlin.String | Audit id
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : GeoAuditRunList = apiInstance.listGeoAuditRuns(geoAuditId, projectId, page, perPage, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#listGeoAuditRuns")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#listGeoAuditRuns")
    e.printStackTrace()
}
```

### Parameters
| **geoAuditId** | **kotlin.String**| Audit id | |
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**GeoAuditRunList**](GeoAuditRunList.md)

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

<a id="listGeoAudits"></a>
# **listGeoAudits**
> GeoAuditList listGeoAudits(projectId, auditType, status, cadence, page, perPage)

List GEO audits

Lists the project&#39;s audits, most recently updated first. Archived audits are left out unless status&#x3D;archived.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val auditType : kotlin.String = auditType_example // kotlin.String | 
val status : kotlin.String = status_example // kotlin.String | 
val cadence : kotlin.String = cadence_example // kotlin.String | 
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
try {
    val result : GeoAuditList = apiInstance.listGeoAudits(projectId, auditType, status, cadence, page, perPage)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#listGeoAudits")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#listGeoAudits")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **auditType** | **kotlin.String**|  | [optional] [enum: agent_readiness, robots_txt, crawlability, schema, content_readiness, discoverability, site_structure] |
| **status** | **kotlin.String**|  | [optional] [enum: active, paused, archived] |
| **cadence** | **kotlin.String**|  | [optional] [enum: once, weekly, monthly] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |

### Return type

[**GeoAuditList**](GeoAuditList.md)

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

<a id="runGeoAudit"></a>
# **runGeoAudit**
> GeoAuditRunResponse runGeoAudit(geoAuditId, projectId)

Run a GEO audit now

Starts a run and returns it with status queued; poll GET /geo_audits/{geo_audit_id}/runs/{sequence} until status is completed, failed or unreachable. Limited to 6 manual runs per audit per rolling hour and 200 per account per day (ERR_LIMIT_REACHED); scheduled runs do not count. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val geoAuditId : kotlin.String = geoAuditId_example // kotlin.String | Audit id
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    val result : GeoAuditRunResponse = apiInstance.runGeoAudit(geoAuditId, projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#runGeoAudit")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#runGeoAudit")
    e.printStackTrace()
}
```

### Parameters
| **geoAuditId** | **kotlin.String**| Audit id | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

### Return type

[**GeoAuditRunResponse**](GeoAuditRunResponse.md)

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

<a id="updateGeoAudit"></a>
# **updateGeoAudit**
> GeoAuditResponse updateGeoAudit(id, geoAuditUpdateRequest)

Update a GEO audit

Updates the schedule, the email alerts or the status. Making an audit recurring or resuming it counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Optimization.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val id : kotlin.String = id_example // kotlin.String | Audit id
val geoAuditUpdateRequest : GeoAuditUpdateRequest =  // GeoAuditUpdateRequest | 
try {
    val result : GeoAuditResponse = apiInstance.updateGeoAudit(id, geoAuditUpdateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#updateGeoAudit")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#updateGeoAudit")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.String**| Audit id | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **geoAuditUpdateRequest** | [**GeoAuditUpdateRequest**](GeoAuditUpdateRequest.md)|  | |

### Return type

[**GeoAuditResponse**](GeoAuditResponse.md)

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

<a id="updateGeoAuditIssue"></a>
# **updateGeoAuditIssue**
> GeoAuditIssueResponse updateGeoAuditIssue(geoAuditId, id, geoAuditIssueUpdateRequest)

Accept or reopen a GEO audit issue

Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Optimization.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = GEOAuditsApi()
val geoAuditId : kotlin.String = geoAuditId_example // kotlin.String | Audit id
val id : kotlin.Int = 56 // kotlin.Int | Issue id
val geoAuditIssueUpdateRequest : GeoAuditIssueUpdateRequest =  // GeoAuditIssueUpdateRequest | 
try {
    val result : GeoAuditIssueResponse = apiInstance.updateGeoAuditIssue(geoAuditId, id, geoAuditIssueUpdateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling GEOAuditsApi#updateGeoAuditIssue")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling GEOAuditsApi#updateGeoAuditIssue")
    e.printStackTrace()
}
```

### Parameters
| **geoAuditId** | **kotlin.String**| Audit id | |
| **id** | **kotlin.Int**| Issue id | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **geoAuditIssueUpdateRequest** | [**GeoAuditIssueUpdateRequest**](GeoAuditIssueUpdateRequest.md)|  | |

### Return type

[**GeoAuditIssueResponse**](GeoAuditIssueResponse.md)

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

