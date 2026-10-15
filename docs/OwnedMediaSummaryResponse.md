
# OwnedMediaSummaryResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  [optional] |
| **provider** | **kotlin.String** |  |  [optional] |
| **from** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **to** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  [optional] |
| **connected** | **kotlin.Boolean** | Whether a profile is claimed on the platform (on overview, on any platform) |  [optional] |
| **kpis** | [**OwnedMediaKpis**](OwnedMediaKpis.md) |  |  [optional] |
| **previous** | [**OwnedMediaSummaryResponsePrevious**](OwnedMediaSummaryResponsePrevious.md) |  |  [optional] |
| **changes** | [**OwnedMediaKpiChanges**](OwnedMediaKpiChanges.md) |  |  [optional] |
| **weekly** | [**kotlin.collections.List&lt;OwnedMediaWeek&gt;**](OwnedMediaWeek.md) |  |  [optional] |
| **byModel** | [**kotlin.collections.List&lt;OwnedMediaModelShare&gt;**](OwnedMediaModelShare.md) | Null for provider&#x3D;overview |  [optional] |
| **byCountry** | [**kotlin.collections.List&lt;OwnedMediaCountryShare&gt;**](OwnedMediaCountryShare.md) | Null for provider&#x3D;overview |  [optional] |
| **contentTypes** | [**kotlin.collections.List&lt;OwnedMediaContentTypeShare&gt;**](OwnedMediaContentTypeShare.md) | Social and YouTube providers only |  [optional] |
| **ageBuckets** | [**kotlin.collections.List&lt;OwnedMediaAgeBucketShare&gt;**](OwnedMediaAgeBucketShare.md) | Social and YouTube providers only. Posts or videos without a known publication date are left out |  [optional] |
| **stores** | [**kotlin.collections.List&lt;OwnedMediaStoreTotals&gt;**](OwnedMediaStoreTotals.md) | provider&#x3D;mobile_apps only |  [optional] |
| **platforms** | [**kotlin.collections.List&lt;OwnedMediaPlatformRollup&gt;**](OwnedMediaPlatformRollup.md) | provider&#x3D;overview only, one row per platform the caller can read |  [optional] |
| **requestId** | **kotlin.String** |  |  [optional] |



