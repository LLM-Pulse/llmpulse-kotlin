
# OwnedMediaPlatformRollup

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **provider** | [**inline**](#Provider) |  |  [optional] |
| **connected** | **kotlin.Boolean** |  |  [optional] |
| **total** | **kotlin.Int** |  |  [optional] |
| **yours** | **kotlin.Int** |  |  [optional] |
| **sharePct** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **weekly** | [**kotlin.collections.List&lt;OwnedMediaPlatformRollupWeeklyInner&gt;**](OwnedMediaPlatformRollupWeeklyInner.md) |  |  [optional] |
| **activity** | [**kotlin.collections.List&lt;OwnedMediaPlatformActivityPeriod&gt;**](OwnedMediaPlatformActivityPeriod.md) | One date/citation row per project tracking period that holds a run inside the window; a period whose runs all fell before from is left out |  [optional] |


<a id="Provider"></a>
## Enum: provider
| Name | Value |
| ---- | ----- |
| provider | youtube, mobile_apps, instagram, facebook, tiktok, linkedin, trustpilot, reddit |



