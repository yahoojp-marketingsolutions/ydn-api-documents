# ReportSelector
ReportSelectorオブジェクトは、操作の対象とするレポートです。
### Service
+ [ReportService](../services/ReportService.md)

| フィールド | データ型 | 説明 | 制限 | 
|---|---|---|---|
| accountId| xsd: long| アカウントIDです。| Req |
| reportJobIds[]| xsd: long| レポートジョブIDです。| Opt |
| reportJobStatuses| enum <a href="../data/ReportJobStatus.md">ReportJobStatus[]</a>| レポートジョブの処理状況を確認します。| Opt |
| paging| <a href="../data/Paging.md">Paging</a>| レスポンスとして戻されるページです。| Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
