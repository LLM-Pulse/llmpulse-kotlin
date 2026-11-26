
# PeecExportImportResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **projectId** | **kotlin.Int** |  |  |
| **importId** | **kotlin.Int** |  |  |
| **status** | [**inline**](#Status) | The import was accepted and finishes in the background |  |
| **prompts** | **kotlin.Int** | Distinct prompts of the file, per country and language; each becomes a tracked prompt of the project |  |
| **newPrompts** | **kotlin.Int** | The prompts the project does not hold yet, counted against the plan |  |
| **plannedAnswers** | **kotlin.Int** | Weekly answers the import files (prompts x tracked AI models x weeks) |  |
| **models** | **kotlin.collections.Map&lt;kotlin.String, kotlin.String&gt;** | Each AI model name of the file that is imported, with the tracked AI model its answers are filed under |  |
| **skippedModels** | **kotlin.collections.List&lt;kotlin.String&gt;** | AI model names of the file whose answers are skipped, because the account does not track them |  |
| **detectedBrands** | **kotlin.collections.List&lt;kotlin.String&gt;** | Brand names the export&#39;s mentions column lists (up to 50), none of them created as competitors |  |
| **appUrl** | [**java.net.URI**](java.net.URI.md) | Opens the project&#39;s prompts in the app |  |
| **requestId** | **kotlin.String** |  |  |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | started |



