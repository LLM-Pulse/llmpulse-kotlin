
# ShoppingRow

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **currency** | **kotlin.String** | Currency code the prices are in; null when no price names one |  |
| **minPrice** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  |
| **maxPrice** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  |
| **avgRating** | [**java.math.BigDecimal**](java.math.BigDecimal.md) |  |  |
| **appearances** | **kotlin.Int** |  |  |
| **productKey** | **kotlin.String** | Stable grouping key of the product: its external id, else title: and the lowercased title (view&#x3D;products) |  [optional] |
| **title** | **kotlin.String** |  |  [optional] |
| **domain** | **kotlin.String** |  |  [optional] |
| **url** | **kotlin.String** |  |  [optional] |
| **merchants** | **kotlin.String** | The merchants the product card names (view&#x3D;products) |  [optional] |
| **merchant** | **kotlin.String** | The merchant (view&#x3D;merchants) |  [optional] |
| **products** | **kotlin.Int** | Distinct products the merchant sold (view&#x3D;merchants) |  [optional] |
| **currencyCount** | **kotlin.Int** | Currencies the product was priced in; above 1 the row reports its highest-priced listing (view&#x3D;products) |  [optional] |
| **avgPrice** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Average price in currency (view&#x3D;merchants) |  [optional] |
| **ratingVotes** | **kotlin.Int** | Most rating votes any listing of the product showed (view&#x3D;products) |  [optional] |
| **isClient** | **kotlin.Boolean** | Whether the product is identified as your brand&#39;s own (view&#x3D;products) |  [optional] |
| **bestRank** | **kotlin.Int** | Best rank the product got in a card list (view&#x3D;products) |  [optional] |
| **models** | [**inline**](#kotlin.collections.List&lt;Models&gt;) | Models that showed the product (view&#x3D;products) |  [optional] |
| **lastSeenAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | The latest answer that showed the product (view&#x3D;products) |  [optional] |


<a id="kotlin.collections.List<Models>"></a>
## Enum: models
| Name | Value |
| ---- | ----- |
| models | chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode, bing_ai_overview |



