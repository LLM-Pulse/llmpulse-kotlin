
# SourceRecord

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **promptExecutionId** | **kotlin.Int** |  |  |
| **domain** | **kotlin.String** | Registrable domain of the cited URL |  |
| **url** | **kotlin.String** | Normalized cited URL (tracking parameters and fragment removed) |  |
| **urlSha256** | **kotlin.String** | Key of the cited page, as GET /citation_intelligence/urls/{url_sha256} takes it |  |
| **position** | **kotlin.Int** | Rank of the citation in the answer; 0 for a background source reference with no visible rank |  |
| **sourceType** | **kotlin.String** | owned (the project&#39;s domains), competitor or third_party |  |
| **isGooglePlayLink** | **kotlin.Boolean** |  |  |
| **isAppStoreLink** | **kotlin.Boolean** |  |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |



