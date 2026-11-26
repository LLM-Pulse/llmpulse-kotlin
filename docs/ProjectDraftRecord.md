
# ProjectDraftRecord

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **draftId** | **kotlin.String** | Draft id (draft_...) |  |
| **status** | **kotlin.String** | open, finalized or expired |  |
| **currentStep** | **kotlin.String** | The next step to submit (details, prompts, competitors, owned_media), or ready when the draft can be finalized |  |
| **stepsCompleted** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  |
| **stepsRemaining** | **kotlin.collections.List&lt;kotlin.String&gt;** | Required steps not submitted yet |  |
| **optionalSteps** | **kotlin.collections.List&lt;kotlin.String&gt;** | Steps the plan allows but finalize does not require (owned_media from Growth) |  |
| **finalizable** | **kotlin.Boolean** |  |  |
| **websiteUrl** | **kotlin.String** |  |  |
| **mainCountry** | **kotlin.String** |  |  |
| **mainLanguage** | **kotlin.String** |  |  |
| **useSubdomain** | **kotlin.Boolean** |  |  |
| **name** | **kotlin.String** | Null until the details step |  |
| **brandName** | **kotlin.String** |  |  |
| **description** | **kotlin.String** |  |  |
| **industry** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  |
| **matchingNames** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  |
| **prompts** | **kotlin.collections.List&lt;kotlin.String&gt;** |  |  |
| **competitors** | [**kotlin.collections.List&lt;ProjectDraftRecordCompetitorsInner&gt;**](ProjectDraftRecordCompetitorsInner.md) |  |  |
| **ownedMedia** | [**ProjectDraftRecordOwnedMedia**](ProjectDraftRecordOwnedMedia.md) |  |  |
| **weeklyEmailSubscribed** | **kotlin.Boolean** |  |  |
| **externalIdentifier** | **kotlin.String** |  |  |
| **executePromptsImmediately** | **kotlin.Boolean** |  |  |
| **projectId** | **kotlin.Int** | The project the draft became; null until finalized |  |
| **expiresAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |



