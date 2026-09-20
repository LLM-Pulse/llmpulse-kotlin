
# UpdateProjectRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **brandName** | **kotlin.String** | Brand name used to detect mentions. Applies to future runs; it does not rewrite history |  [optional] |
| **description** | **kotlin.String** | What the brand does. Context for Recommendations and GEO Writer (Brand Book) |  [optional] |
| **industry** | **kotlin.String** | Single industry key (e.g. SAAS); unknown keys are rejected |  [optional] |
| **businessModel** | **kotlin.String** | Business model key (e.g. B2B_SAAS); unknown keys are rejected |  [optional] |
| **businessModelOther** | **kotlin.String** | Free-text business model, only accepted when business_model is OTHER; rejected against any other key |  [optional] |
| **targetAudience** | **kotlin.String** | Who the brand sells to (Brand Book) |  [optional] |
| **brandVoice** | **kotlin.String** | Tone of voice guidance for generated content (Brand Book) |  [optional] |
| **goals** | **kotlin.String** | What the brand wants to achieve. Context for GEO Writer and prompt suggestions |  [optional] |
| **primaryProducts** | **kotlin.collections.List&lt;kotlin.String&gt;** | Full replacement list of the main products or services |  [optional] |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** | FULL replacement list of the brand-name variants used to detect mentions; send every variant to keep |  [optional] |



