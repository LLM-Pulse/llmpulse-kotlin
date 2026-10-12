
# ProjectUpdateResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **project** | [**ProjectProfile**](ProjectProfile.md) |  |  |
| **updatedFields** | **kotlin.collections.List&lt;kotlin.String&gt;** | The fields the request sent |  |
| **rematching** | **kotlin.Boolean** | True when a matching_names or additional_owned_domains change started a background recalculation of past answers; further edits are rejected until it finishes |  |
| **note** | **kotlin.String** | What the change does to mention detection, citation ownership and historical numbers |  |
| **requestId** | **kotlin.String** |  |  |



