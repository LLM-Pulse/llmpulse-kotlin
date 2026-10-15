# CompetitorsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCompetitor**](CompetitorsApi.md#createCompetitor) | **POST** /competitors | Add a competitor |
| [**deleteCompetitor**](CompetitorsApi.md#deleteCompetitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**getCompetitorDetails**](CompetitorsApi.md#getCompetitorDetails) | **GET** /dimensions/competitors/{id} | Competitor details |
| [**listCompetitorSuggestions**](CompetitorsApi.md#listCompetitorSuggestions) | **GET** /competitors/suggestions | List competitor suggestions |
| [**listCompetitors**](CompetitorsApi.md#listCompetitors) | **GET** /dimensions/competitors | List competitors |
| [**updateCompetitor**](CompetitorsApi.md#updateCompetitor) | **PATCH** /competitors/{id} | Update a competitor |


<a id="createCompetitor"></a>
# **createCompetitor**
> CompetitorCreateResponse createCompetitor(createCompetitorRequest)

Add a competitor

Adds a competitor with its own citation URL matching rule. Honours the per-plan max competitors cap. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CompetitorsApi()
val createCompetitorRequest : CreateCompetitorRequest =  // CreateCompetitorRequest | 
try {
    val result : CompetitorCreateResponse = apiInstance.createCompetitor(createCompetitorRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling CompetitorsApi#createCompetitor")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CompetitorsApi#createCompetitor")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createCompetitorRequest** | [**CreateCompetitorRequest**](CreateCompetitorRequest.md)|  | |

### Return type

[**CompetitorCreateResponse**](CompetitorCreateResponse.md)

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

<a id="deleteCompetitor"></a>
# **deleteCompetitor**
> deleteCompetitor(id, projectId)

Delete a competitor

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; a background job then deletes its mentions, citations, sentiment and share of voice history. Its ads, shopping products, local businesses and brand entities are kept and move to the project or another competitor they match, or stay unattributed. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CompetitorsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    apiInstance.deleteCompetitor(id, projectId)
} catch (e: ClientException) {
    println("4xx response calling CompetitorsApi#deleteCompetitor")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CompetitorsApi#deleteCompetitor")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
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
 - **Accept**: application/json

<a id="getCompetitorDetails"></a>
# **getCompetitorDetails**
> CompetitorDetails getCompetitorDetails(id, projectId)

Competitor details

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CompetitorsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
try {
    val result : CompetitorDetails = apiInstance.getCompetitorDetails(id, projectId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling CompetitorsApi#getCompetitorDetails")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CompetitorsApi#getCompetitorDetails")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int**| Project ID | |

### Return type

[**CompetitorDetails**](CompetitorDetails.md)

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

<a id="listCompetitorSuggestions"></a>
# **listCompetitorSuggestions**
> CompetitorSuggestionsResponse listCompetitorSuggestions(projectId, basis, query, page, perPage, output)

List competitor suggestions

The two lists of the Suggested tab of the Competitors page. &#x60;basis&#x3D;brands&#x60; (default) returns the competing brands the AI discovery proposed that are not tracked or rejected yet, with the names it would match and, when counted, how many answers name it (&#x60;mentions&#x60;). &#x60;basis&#x3D;citations&#x60; returns the domains AI answers cite most that are not your own or tracked yet, with how many answers cite each (&#x60;citations&#x60;). &#x60;discovery&#x60; tells whether a discovery run is still loading. Read-only: it never starts a discovery run, which the page starts from its Discover button. Add a suggestion with POST /competitors.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CompetitorsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val basis : kotlin.String = basis_example // kotlin.String | 
val query : kotlin.String = query_example // kotlin.String | Only suggestions whose brand name or domain contains this text
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : CompetitorSuggestionsResponse = apiInstance.listCompetitorSuggestions(projectId, basis, query, page, perPage, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling CompetitorsApi#listCompetitorSuggestions")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CompetitorsApi#listCompetitorSuggestions")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **basis** | **kotlin.String**|  | [optional] [default to Basis.brands] [enum: brands, citations] |
| **query** | **kotlin.String**| Only suggestions whose brand name or domain contains this text | [optional] |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**CompetitorSuggestionsResponse**](CompetitorSuggestionsResponse.md)

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

<a id="listCompetitors"></a>
# **listCompetitors**
> ListCompetitors200Response listCompetitors(projectId, includeProjectBrand, output)

List competitors

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CompetitorsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val includeProjectBrand : kotlin.Boolean = true // kotlin.Boolean | When true, prepends the project brand with actor_type=project and is_own=true
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    val result : ListCompetitors200Response = apiInstance.listCompetitors(projectId, includeProjectBrand, output)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling CompetitorsApi#listCompetitors")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CompetitorsApi#listCompetitors")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **includeProjectBrand** | **kotlin.Boolean**| When true, prepends the project brand with actor_type&#x3D;project and is_own&#x3D;true | [optional] [default to false] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**ListCompetitors200Response**](ListCompetitors200Response.md)

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

<a id="updateCompetitor"></a>
# **updateCompetitor**
> updateCompetitor(id, updateCompetitorRequest)

Update a competitor

Updates brand_name, the competitor website domain or host, matching_names (full replacement list; the brand name is always included automatically), color and/or the citation URL matching rule. Website domain/host and citation-rule changes share one seven-day cooldown per competitor; other fields remain editable during the cooldown. Name, website or citation-rule changes re-run historical matching in the background: the competitor shows processing&#x3D;true for a few minutes and further edits are rejected meanwhile. Requires a &#x60;read_write&#x60; scope API key.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = CompetitorsApi()
val id : kotlin.Int = 56 // kotlin.Int | 
val updateCompetitorRequest : UpdateCompetitorRequest =  // UpdateCompetitorRequest | 
try {
    apiInstance.updateCompetitor(id, updateCompetitorRequest)
} catch (e: ClientException) {
    println("4xx response calling CompetitorsApi#updateCompetitor")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CompetitorsApi#updateCompetitor")
    e.printStackTrace()
}
```

### Parameters
| **id** | **kotlin.Int**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updateCompetitorRequest** | [**UpdateCompetitorRequest**](UpdateCompetitorRequest.md)|  | |

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

