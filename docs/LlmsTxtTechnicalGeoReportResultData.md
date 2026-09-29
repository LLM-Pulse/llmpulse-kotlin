
# LlmsTxtTechnicalGeoReportResultData

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **llmsTxtContent** | **kotlin.String** | Current llms.txt, manual edits included |  [optional] |
| **llmsFullTxtContent** | **kotlin.String** | Current llms-full.txt, manual edits included |  [optional] |
| **manuallyEditedAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) | When the files were last edited by hand in the app, the API or MCP; null while they are as generated |  [optional] |
| **contentVersion** | **kotlin.String** | Send it back as content_version when editing the files. It changes on every save |  [optional] |
| **originalLlmsTxtContent** | **kotlin.String** | The generated llms.txt, kept from the first manual edit; null while the files are as generated |  [optional] |
| **originalLlmsFullTxtContent** | **kotlin.String** | The generated llms-full.txt, kept from the first manual edit; null while the files are as generated |  [optional] |
| **crawlData** | [**kotlin.Any**](.md) |  |  [optional] |
| **metadata** | [**kotlin.Any**](.md) | Generation details, including output_language_code, the language the files were written in |  [optional] |
| **pagesCrawled** | **kotlin.Int** |  |  [optional] |
| **generationTimeMs** | **kotlin.Int** |  |  [optional] |
| **openaiTokensUsed** | **kotlin.Int** |  |  [optional] |



