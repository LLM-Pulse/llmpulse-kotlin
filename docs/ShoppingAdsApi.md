# ShoppingAdsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listAds**](ShoppingAdsApi.md#listAds) | **GET** /dimensions/ads | List AI ad placements |
| [**listShopping**](ShoppingAdsApi.md#listShopping) | **GET** /dimensions/shopping | List shopping results |


<a id="listAds"></a>
# **listAds**
> listAds(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)

List AI ad placements

Paid placements returned inside AI answers. view&#x3D;advertisers (default) returns one row per advertising domain with its placement count, prompt reach and average and best position; view&#x3D;ads returns the individual placements with title, snippet, position and the prompt that triggered them. Position 1 is the best slot, so a LOWER average position is better. Requires the Scale plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ShoppingAdsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val view : kotlin.String = view_example // kotlin.String | Row shape: one per advertising domain, or one per placement
val owned : kotlin.Boolean = true // kotlin.Boolean | Return only placements identified as the tracked brand's own (view=ads)
val order : kotlin.String = order_example // kotlin.String | Sort field; the allowed set depends on view
val direction : kotlin.String = direction_example // kotlin.String | Sort direction for view=advertisers. Defaults to desc, except avg_position and domain which default to asc.
val query : kotlin.String = query_example // kotlin.String | Case-insensitive substring filter on the ad title, domain or snippet
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : GetTimeseriesCollectionIdParameter =  // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listAds(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)
} catch (e: ClientException) {
    println("4xx response calling ShoppingAdsApi#listAds")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShoppingAdsApi#listAds")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **view** | **kotlin.String**| Row shape: one per advertising domain, or one per placement | [optional] [default to View.advertisers] [enum: advertisers, ads] |
| **owned** | **kotlin.Boolean**| Return only placements identified as the tracked brand&#39;s own (view&#x3D;ads) | [optional] |
| **order** | **kotlin.String**| Sort field; the allowed set depends on view | [optional] [enum: ads, prompts, avg_position, domain, recent, oldest, position] |
| **direction** | **kotlin.String**| Sort direction for view&#x3D;advertisers. Defaults to desc, except avg_position and domain which default to asc. | [optional] [enum: asc, desc] |
| **query** | **kotlin.String**| Case-insensitive substring filter on the ad title, domain or snippet | [optional] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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

<a id="listShopping"></a>
# **listShopping**
> listShopping(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)

List shopping results

Product cards returned inside AI answers. view&#x3D;products (default) returns one row per distinct product, merged across executions, with its appearance count, price range, rating and whether it is yours, plus a currency_count saying how many currencies it was priced in (above 1 means the row reports its highest-priced listing and min_price may be another currency); view&#x3D;merchants returns one row per selling merchant, with a currency field naming the money its price range and average are expressed in (providers price each market in its own currency, so a merchant that sells in more than one reports the currency most of its prices use). Every response also carries a totals block matching the KPI cards in the app, whose avg_price is computed inside the single currency named by avg_price_currency. Requires the Scale plan or above.

### Example
```kotlin
// Import classes:
//import ai.llmpulse.sdk.infrastructure.*
//import ai.llmpulse.sdk.models.*

val apiInstance = ShoppingAdsApi()
val projectId : kotlin.Int = 56 // kotlin.Int | Project ID
val page : kotlin.Int = 56 // kotlin.Int | 
val perPage : kotlin.Int = 56 // kotlin.Int | 
val view : kotlin.String = view_example // kotlin.String | Row shape: one per distinct product, or one per merchant
val owned : kotlin.Boolean = true // kotlin.Boolean | Return only products identified as the tracked brand's own. On view=merchants this narrows to the merchants selling those products; the totals block stays account-wide.
val order : kotlin.String = order_example // kotlin.String | Sort field; the allowed set depends on view
val direction : kotlin.String = direction_example // kotlin.String | 
val query : kotlin.String = query_example // kotlin.String | Case-insensitive substring filter on the product title
val model : kotlin.String = model_example // kotlin.String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
val collectionId : GetTimeseriesCollectionIdParameter =  // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
val countryCode : kotlin.String = countryCode_example // kotlin.String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
val languageCode : kotlin.String = languageCode_example // kotlin.String | One ISO language code or a comma-separated list (e.g. en,es,de)
val prompt : kotlin.Int = 56 // kotlin.Int | Filter by prompt ID
val promptType : kotlin.String = promptType_example // kotlin.String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
val brandKind : kotlin.String = brandKind_example // kotlin.String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
val range : kotlin.Int = 56 // kotlin.Int | Number of days to look back (alternative to from/to)
val from : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | 
val to : java.time.OffsetDateTime = 2013-10-20T19:20:30+01:00 // java.time.OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
val output : kotlin.String = output_example // kotlin.String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
try {
    apiInstance.listShopping(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)
} catch (e: ClientException) {
    println("4xx response calling ShoppingAdsApi#listShopping")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShoppingAdsApi#listShopping")
    e.printStackTrace()
}
```

### Parameters
| **projectId** | **kotlin.Int**| Project ID | |
| **page** | **kotlin.Int**|  | [optional] [default to 1] |
| **perPage** | **kotlin.Int**|  | [optional] [default to 20] |
| **view** | **kotlin.String**| Row shape: one per distinct product, or one per merchant | [optional] [default to View.products] [enum: products, merchants] |
| **owned** | **kotlin.Boolean**| Return only products identified as the tracked brand&#39;s own. On view&#x3D;merchants this narrows to the merchants selling those products; the totals block stays account-wide. | [optional] |
| **order** | **kotlin.String**| Sort field; the allowed set depends on view | [optional] [enum: appearances, price, rating, title, products, avg_price, avg_rating, merchant] |
| **direction** | **kotlin.String**|  | [optional] [default to Direction.desc] [enum: asc, desc] |
| **query** | **kotlin.String**| Case-insensitive substring filter on the product title | [optional] |
| **model** | **kotlin.String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **kotlin.String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **kotlin.String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **kotlin.Int**| Filter by prompt ID | [optional] |
| **promptType** | **kotlin.String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **kotlin.String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **kotlin.Int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **java.time.OffsetDateTime**|  | [optional] |
| **to** | **java.time.OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **output** | **kotlin.String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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

