
# AnalystScoreRow

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **brand** | **kotlin.String** | Brand name; the subject name in a custom study |  |
| **isProject** | **kotlin.Boolean** | Whether it is the project&#39;s own brand; in a custom study, the focus subject |  |
| **model** | [**inline**](#Model) |  |  |
| **reportDate** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  |
| **dimension** | **kotlin.String** | Dimension key, as the dimension filter takes it |  |
| **dimensionName** | **kotlin.String** |  |  |
| **attribute** | **kotlin.String** | Attribute key within the dimension |  |
| **attributeName** | **kotlin.String** |  |  |
| **score** | [**kotlin.Any**](.md) | The 0-100 score as the analyst model wrote it, normally a number, or null when it gave none. Deliberately untyped, as the model&#39;s output is stored without coercion |  |
| **reasoning** | **kotlin.String** | Why the model gave this score; null when it gave no reasoning |  |


<a id="Model"></a>
## Enum: model
| Name | Value |
| ---- | ----- |
| model | chatgpt, perplexity, gemini, deepseek, grok, claude |



