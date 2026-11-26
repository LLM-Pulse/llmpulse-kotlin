
# AllCitationRecord

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** | The citation&#39;s id, unique within its actor_type |  |
| **actorType** | **kotlin.String** | project (your brand) or competitor |  |
| **name** | **kotlin.String** | The project&#39;s brand name (its name when no brand name is set), or the competitor&#39;s brand name |  |
| **domain** | **kotlin.String** | On project rows the host of the cited URL without www. (null when it has no parsable host); on competitor rows the competitor&#39;s bare domain |  |
| **promptId** | **kotlin.Int** |  |  |
| **promptExecutionId** | **kotlin.Int** |  |  |
| **url** | **kotlin.String** | Normalized cited URL (tracking parameters and fragment removed) |  |
| **position** | **kotlin.Int** | Rank of the citation in the answer; 0 for a background source reference with no visible rank |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **competitorId** | **kotlin.Int** | Competitor rows only |  [optional] |



