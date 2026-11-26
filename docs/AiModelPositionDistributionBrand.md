
# AiModelPositionDistributionBrand

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **type** | **kotlin.String** | project or competitor |  |
| **id** | **kotlin.Int** | Project id, or competitor id |  |
| **competitorId** | **kotlin.Int** | Null for the project, the competitor id otherwise |  |
| **name** | **kotlin.String** |  |  |
| **domain** | **kotlin.String** | Bare (scheme-less) domain. Null for the project when it has no URL. |  |
| **buckets** | [**kotlin.collections.List&lt;AiModelPositionDistributionBrandBucketsInner&gt;**](AiModelPositionDistributionBrandBucketsInner.md) | One per position bucket, in order: position_1, position_2_3, position_4_7 and position_8_plus |  |
| **maxStackedValue** | **kotlin.Int** | The brand&#39;s largest mentions count of one period, its buckets added up |  |



