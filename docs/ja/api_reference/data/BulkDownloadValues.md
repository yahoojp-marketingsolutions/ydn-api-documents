# BulkDownloadValues
BulkDownloadValuesオブジェクトは、一括ダウンロードの処理結果を格納するコンテナです。
### Service
+ [BulkService](../services/BulkService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| ReturnValue(inherited)|||
| operationSucceeded| xsd: boolean| 処理結果です。 |
| error| <a href="./Error.md">Error</a>[]| エラーの内容です。 |
| BulkDownloadValues|||
| downloadBulkJob| <a href="./DownloadBulkJob.md"><span>DownloadBulkJob</span></a>| 処理結果を格納するコンテナです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
