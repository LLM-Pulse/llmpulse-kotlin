
# AiModelDeclinedAnswersResponseChartInner

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **date** | [**java.time.LocalDate**](java.time.LocalDate.md) | First day of the tracking period |  |
| **answers** | **kotlin.Int** | Finished runs of the model, declined ones included |  [optional] |
| **declined** | **kotlin.Int** | Answers the model declined |  [optional] |
| **declineRate** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **safetyFilter** | **kotlin.Int** | Answers declined by the model&#39;s own safety filters |  [optional] |
| **safetyFilterRate** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |
| **topicRefusal** | **kotlin.Int** | Answers that declined the topic itself, such as tobacco, gambling or alcohol |  [optional] |
| **topicRefusalRate** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  [optional] |



