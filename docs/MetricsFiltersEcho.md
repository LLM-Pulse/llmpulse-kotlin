
# MetricsFiltersEcho

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **metrics** | **kotlin.collections.List&lt;kotlin.String&gt;** | Requested metrics after alias resolution (mention_rate is echoed as visibility) |  [optional] |
| **granularity** | **kotlin.String** | day, week or month |  [optional] |
| **model** | **kotlin.String** | The model filter, or null when absent or not enabled for the account |  [optional] |
| **collectionId** | **kotlin.String** | The collection_id parameter as sent (one id or a comma-separated list) |  [optional] |
| **collectionIds** | **kotlin.collections.List&lt;kotlin.Int&gt;** |  |  [optional] |
| **domains** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  [optional] |
| **countryCode** | **kotlin.String** | Comma-separated country codes |  [optional] |
| **languageCode** | **kotlin.String** | Comma-separated language codes |  [optional] |
| **prompt** | **kotlin.Int** | The prompt id filter |  [optional] |
| **promptType** | **kotlin.String** | Comma-separated prompt types |  [optional] |
| **brandKind** | **kotlin.String** |  |  [optional] |
| **competitors** | **kotlin.collections.List&lt;kotlin.Int&gt;** | Competitor ids from the competitors parameter; empty when it was not given |  [optional] |
| **includeProject** | **kotlin.Boolean** |  |  [optional] |
| **query** | **kotlin.String** | Only present when a query filter was given |  [optional] |



