
# TrustpilotReplies

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **reviewsHeld** | **kotlin.Int** | Reviews held for the profile |  [optional] |
| **repliedCount** | **kotlin.Int** | Reviews held that the brand replied to |  [optional] |
| **notRepliedCount** | **kotlin.Int** | Reviews held that the brand has not replied to |  [optional] |
| **replyRatePct** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | replied_count over reviews_held, on a 0-100 scale; null when no review is held |  [optional] |
| **medianReplyHours** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Median hours from publication to reply over the replied reviews held that carry both dates (a reply dated before its review is left out); null when there is none |  [optional] |



