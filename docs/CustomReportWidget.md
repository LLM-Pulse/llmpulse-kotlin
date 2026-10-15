
# CustomReportWidget

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **key** | **kotlin.String** |  |  |
| **label** | **kotlin.String** |  |  |
| **kind** | [**inline**](#Kind) |  |  |
| **width** | [**inline**](#Width) |  |  |
| **available** | **kotlin.Boolean** | false when the widget&#39;s data source (web analytics, agent analytics, owned media) is not connected |  |
| **&#x60;data&#x60;** | [**kotlin.collections.Map&lt;kotlin.String, kotlin.Any&gt;**](kotlin.Any.md) | Shaped by kind. timeseries: series [{ name, color, points [{ date, value }] }]. donut: slices [{ name, value, color }]. bar: bars [{ label, value, color }]. kpi_grid: values and changes (null unless the report compares with the previous period). table: rows, one object per row. Null when the widget is not available. |  [optional] |


<a id="Kind"></a>
## Enum: kind
| Name | Value |
| ---- | ----- |
| kind | kpi_grid, timeseries, donut, bar, table |


<a id="Width"></a>
## Enum: width
| Name | Value |
| ---- | ----- |
| width | half, full |



