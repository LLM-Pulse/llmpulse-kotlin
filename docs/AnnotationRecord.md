
# AnnotationRecord

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** |  |  |
| **title** | **kotlin.String** |  |  |
| **description** | **kotlin.String** |  |  |
| **annotationDate** | [**java.time.LocalDate**](java.time.LocalDate.md) |  |  |
| **color** | **kotlin.String** |  |  |
| **category** | **kotlin.String** | user (written by a person) or system (added by the platform) |  |
| **origin** | **kotlin.String** | manual, platform (a platform-wide event) or automation (a project change recorded automatically) |  |
| **annotationCategory** | [**AnnotationRecordAnnotationCategory**](AnnotationRecordAnnotationCategory.md) |  |  |
| **editable** | **kotlin.Boolean** | Whether the requesting user may update or delete it |  |
| **createdAt** | [**java.time.OffsetDateTime**](java.time.OffsetDateTime.md) |  |  |



