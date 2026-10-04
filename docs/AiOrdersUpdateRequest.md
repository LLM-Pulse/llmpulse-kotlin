
# AiOrdersUpdateRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **platform** | [**inline**](#Platform) |  |  |
| **currency** | **kotlin.String** | ISO 4217 code, e.g. EUR |  |
| **from** | [**java.time.LocalDate**](java.time.LocalDate.md) | First day of the window this push replaces |  |
| **to** | [**java.time.LocalDate**](java.time.LocalDate.md) | Last day of the window; at most 400 days after from |  |
| **days** | [**kotlin.collections.List&lt;AiOrdersUpdateRequestDaysInner&gt;**](AiOrdersUpdateRequestDaysInner.md) |  |  |


<a id="Platform"></a>
## Enum: platform
| Name | Value |
| ---- | ----- |
| platform | shopify |



