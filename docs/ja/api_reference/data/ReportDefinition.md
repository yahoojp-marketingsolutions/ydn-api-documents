# ReportDefinition
ReportDefinitionオブジェクトは、レポート定義を表します。
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| reportId| long| 1| 0| ○| -| Req| Req| レポートIDです。 |
| accountId| long| 1| 0| ○| -| Req| Req| アカウントIDです。 |
| campaignId| long| 1| 0| ○| Opt| -| -| キャンペーンIDです。 |
| reportName| string| 1| 0| ○| Opt| Opt| -| レポート名です。 |
| reportType| enum <a href="./ReportType.md">ReportType</a>| 1| 0| ○| Req| -| -| レポート種別です。 |
| dateRangeType| enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a>| 1| 0| ○| Req| -| -| 集計期間種別です。 |
| dateRange| <a href="./ReportDateRange.md">ReportDateRange</a>| 1| 0| ○| Opt| -| -| 集計期間です。 |
| sort| string| 1| 0| ○| Opt| -| -| ソートです。 |
| segments[]| enum <a href="./ReportSegment.md">ReportSegment</a>| unbounded| 0| ○| Opt| -| -| 集計分割指定です。 |
| fields[]| string| unbounded| 0| ○| Opt| -| -| 表示項目です。 |
| format| enum <a href="./ReportDownloadFormat.md">ReportDownloadFormat</a>| 1| 0| ○| Opt| -| -| ファイル出力形式です。 |
| encode| enum <a href="./ReportDownloadEncode.md">ReportDownloadEncode</a>| 1| 0| ○| Opt| -| -| 出力文字コードです。 |
| zip| enum <a href="./ReportZip.md">ReportZip</a>| 1| 0| ○| Opt| -| -| zip化の有無です。 |
| lang| enum <a href="./ReportLang.md">ReportLang</a>| 1| 0| ○| Opt| -| -| 出力言語です。 |
| frequency| enum <a href="./ReportFrequency.md">ReportFrequency</a>| 1| 0| ○| Opt| Opt| -| 定期レポート作成タイミングです。 |
| specifyDay| int| 1| 0| ○| Opt| Opt| -| 定期レポート作成日です。 |
| addTemplate| enum <a href="./ReportAddTemplate.md">ReportAddTemplate</a>| 1| 0| ○| Opt| -| -| テンプレートフラグです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
