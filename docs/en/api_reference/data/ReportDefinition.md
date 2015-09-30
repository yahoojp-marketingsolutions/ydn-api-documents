# ReportDefinition
The ReportDefinition object serves report definitions.
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| reportId| xsd: long| The report definition ID.| -| Req| Req |
| accountId| xsd: long| The account ID.| -| Req| Req |
| campaignId| xsd: long| The campaign ID.| Opt| -| - |
| reportName| xsd: string| Report name to be set by user.| Opt| Opt| - |
| reportType| enum <a href="../data/ReportType.md">ReportType</a>| The report type.| Req| -| - |
| dateRangeType| enum <a href="../data/ReportDateRangeType.md">ReportDateRangeType</a>| The compilation target period for a defined report.| Req| -| - |
| dateRange| <a href="../data/ReportDateRange.md">ReportDateRange</a>| The date range for report compilation to be set by user.<br>                        This item is required when DataRangeType is set to "CUSTOM_DATE".| Opt| -| - |
| sort| xsd: string| Selects a field name and sorts in ascending or descending order. A sorting method can be selected by choosing the "+" or "-" single-byte characters at the top of the field name. <br>                        Acquire a field name with getReportFields.| Opt| -| - |
| segments[]| enum <a href="../data/ReportSegment.md">ReportSegment</a>| Filter conditions for grouping.| Opt| -| - |
| fields[]| xsd: string| The field (report item name).<br>                        Selects values acquired with getReportFields.<br>                        * Field (report item name) order cannot be changed. Set in the order acquired in with getReportFields during a request.| Opt| -| - |
| format| enum <a href="../data/ReportDownloadFormat.md">ReportDownloadFormat</a>| File format for the defined download report.| Opt| -| - |
| encode| enum <a href="../data/ReportDownloadEncode.md">ReportDownloadEncode</a>| Encoding for the defined download report.| Opt| -| - |
| zip| enum <a href="./ReportZip.md">ReportZip</a>| Whether or not a compressed file exists for the defined report.| Opt| -| - |
| lang| enum <a href="../data/ReportLang.md">ReportLang</a>| Language for the defined column name.| Opt| -| - |
| frequency| enum <a href="./ReportFrequency%20.md">ReportFrequency</a>| Schedule of report creation.| Opt| Opt| - |
| specifyDay| int| Selects day for report.| Opt| Opt| - |
| addTemplate| enum <a href="./ReportAddTemplate.md">ReportAddTemplate</a>| Set the definition for a template flag.| Opt| -| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
