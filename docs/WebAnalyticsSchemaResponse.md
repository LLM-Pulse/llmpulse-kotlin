
# WebAnalyticsSchemaResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **provider** | [**inline**](#Provider) | The connected web analytics provider. |  [optional] |
| **&#x60;property&#x60;** | **kotlin.String** | The property, site, report suite (rsid:...), data view (dataview:...) or project every query runs on. |  [optional] |
| **queryLanguage** | **kotlin.String** | The native query format the provider accepts. |  [optional] |
| **docsUrl** | **kotlin.String** | The provider&#39;s reference for that format. |  [optional] |
| **allowedFields** | **kotlin.collections.List&lt;kotlin.String&gt;** | Top-level query fields that are forwarded. |  [optional] |
| **rules** | **kotlin.collections.List&lt;kotlin.String&gt;** | What the bridge enforces and the provider&#39;s main constraints. |  [optional] |
| **example** | [**kotlin.collections.Map&lt;kotlin.String, kotlin.Any&gt;**](kotlin.Any.md) | A worked query to adapt. |  [optional] |
| **fields** | [**kotlin.collections.Map&lt;kotlin.String, kotlin.Any&gt;**](kotlin.Any.md) | The provider&#39;s live field list where it offers one: GA4 dimensions and metrics with custom definitions, Adobe ids, Matomo report methods, PostHog event names, the Plausible catalog. Null when the provider did not return it. |  [optional] |
| **fieldsUnavailable** | **kotlin.String** | Present when the field list could not be read; the format and example still apply. |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |


<a id="Provider"></a>
## Enum: provider
| Name | Value |
| ---- | ----- |
| provider | google_analytics, adobe_analytics, matomo, posthog, plausible, piano |



