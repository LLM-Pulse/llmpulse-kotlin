
# AiOrdersUpdateRequestDaysInner

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **day** | [**java.time.LocalDate**](java.time.LocalDate.md) | Must fall inside from..to |  |
| **referrer** | **kotlin.String** | Raw referring host or utm_source of the order&#39;s first visit, e.g. chatgpt.com. Entries that are not an AI assistant are ignored |  |
| **orders** | **kotlin.Int** |  |  |
| **revenue** | **kotlin.String** | Non-negative decimal amount in currency, e.g. 120.50. A JSON number is accepted too |  |



