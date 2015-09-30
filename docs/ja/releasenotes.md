# リリースノート
## リリースバージョン　　
5.0 (WSDLバージョン: 5.0.0)
## バージョンアップの種類　　
メジャーバージョンアップ 
## 本リリースの主な内容
#### 1. サイトリターゲティング機能の改善 
サイトリターゲティング機能の変更および追加を行いました。  
  
※ターゲットリストの設定上限数を変更しました。（1アカウントあたり100個→300個）  
※配信除外リストの設定が可能になりました。（配信対象リストと除外リストが両方設定された場合、配信除外リストの設定が優先されます。）  
※ターゲットリストの条件にリファラURLの設定が可能になりました。  
※ターゲットリストの条件において、URLの文字長を短縮しました。（1024byte → 250byte）   
  
* 対象ウェブサービス  
 * [AdGroupTargetService](/docs/ja/api_reference/services/AdGroupTargetService.md)
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)
  
* 対象データオブジェクト  
 * [SiteRetargetingTarget](/docs/ja/api_reference/data/SiteRetargetingTarget.md)
 * [RuleCondition](/docs/ja/api_reference/data/RuleCondition.md)
  
* 対象Enumerations  
 * [TargetListDeliverType](/docs/ja/api_reference/data/TargetListDeliverType.md)
 * [RuleType](/docs/ja/api_reference/data/RuleType.md)
 
#### 2. 広告の追加  
多くのデバイスや掲載面に対応出来る2種類の広告を追加しました。  
・RESPONSIVE_AD（レスポンシブ）  
・STATIC_FRAME_AD（広告枠サイズ固定）  
  
※サイトカテゴリー、プレイスメントターゲティング以外のターゲティング設定をご利用いただけます。  
※配信される広告表示枠の大きさに合わせて画像のサイズが調整（縮小）されます。  
※RESPONSIVE_ADの場合、配信される広告表示枠の形に合わせて画像がトリミングされます。  
※RESPONSIVE_ADの入稿仕様は以下の通りです。  
・タイトル：25文字（必須）  
・説明文：90文字（必須）  
・表示URL：4～50 文字（必須）  
・リンクURL：11～1024文字（必須）  
・画像：300×300、1200×628*（必須）  
　※広告掲載方式「ターゲティング」の掲載フォーマット「テンプレート」内の1200×628は、現在ご利用いただけません。  
　入稿が可能になり次第、ご連絡します。  
・主体者表記：20文字（必須）  
・ボタンのテキスト（任意）  
・ロゴ画像：180×180（任意）  
  
※STATIC_FRAME_ADは、3種類の広告レイアウトが利用可能です。  
  
<table class="standard">
  <tbody><tr>
    <th>レイアウト名</th>
    <th>入稿仕様</th>
  </tr>
  <tr>
    <td>SQUARE_BANNER_TOP</td>
    <td>・タイトル：15文字（必須）<br>
・説明文：なし<br>
・表示URL：4～29 文字（必須）<br>
・リンクURL：11～1024文字（必須）<br>
・画像：300×300（必須）<br>
・主体者表記：20文字（必須）<br>
・ボタン（任意）<br>
・ロゴ：180×180（任意）<br>
・カラーテーマ設定（任意）</td>
  </tr>
  <tr>
    <td>WIDE_BANNER_TOP</td>
    <td>・タイトル：20文字（必須）<br>
・説明文：38文字（必須）<br>
・表示URL：4～29 文字（必須）<br>
・リンクURL：11～1024文字（必須）<br>
・画像：1200×628（必須）<br>
・主体者表記：20文字（必須）<br>
・ロゴ：180×180（任意）<br>
・カラーテーマ設定（任意）</td>
  </tr>
  <tr>
    <td>WIDE_BANNER_MIDDLE</td>
    <td>・タイトル：20文字（必須）<br>
・説明文：25文字（必須）<br>
・表示URL：4～29 文字（必須）<br>
・リンクURL：11～1024文字（必須）<br>
・画像：300×300（必須）<br>
・主体者表記：20文字（必須）<br>
・ボタン（任意）<br>
・ロゴ：180×180（任意）<br>
・カラーテーマ設定（任意）</td>
  </tr>
</tbody></table>
  
* 対象ウェブサービス  
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [MediaService](/docs/ja/api_reference/services/MediaService.md)
 * [DictionaryService](/docs/ja/api_reference/services/DictionaryService.md)
 * [PlacementUrlIdeaService](/docs/ja/api_reference/services/PlacementUrlIdeaService.md)
  
* 対象データオブジェクト  
 * [AdGroupAd](/docs/ja/api_reference/data/AdGroupAd.md)
 * [ResponsiveAd](/docs/ja/api_reference/data/ResponsiveAd.md)
 * [StaticFrameAd](/docs/ja/api_reference/data/StaticFrameAd.md)
 * [MediaRecord](/docs/ja/api_reference/data/MediaRecord.md)
 * [ImageMedia](/docs/ja/api_reference/data/ImageMedia.md)
 * [ColorSetSelector](/docs/ja/api_reference/data/ColorSetSelector.md)
 * [ColorSetPage](/docs/ja/api_reference/data/ColorSetPage.md)
 * [ColorSetValues](/docs/ja/api_reference/data/ColorSetValues.md)
 * [ColorSet](/docs/ja/api_reference/data/ColorSet.md)
 * [PlacementUrlIdeaSelector](/docs/ja/api_reference/data/PlacementUrlIdeaSelector.md)
 * [AdFormatConditions](/docs/ja/api_reference/data/AdFormatConditions.md)
  
* 対象Enumerations  
 * [AdType](/docs/ja/api_reference/data/AdType.md)
 * [AdLayout](/docs/ja/api_reference/data/AdLayout.md)
 * [ButtonText](/docs/ja/api_reference/data/ButtonText.md)
 * [LogoFlg](/docs/ja/api_reference/data/LogoFlg.md)
 * [ColorElement](/docs/ja/api_reference/data/ColorElement.md)

#### 3. Serviceの変更による各Versionへの影響  
<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.4.7以前</p></th>
    <th valign="top"><p>Ver.5.0</p></th>
  </tr>

  <tr>
    <td><p>AdGroupTargetService</p></td>
    <td><p>■APIIF変更なし<br>
・サイトリターゲティングの設定情報に「配信除外のターゲットリスト」が1つだけ設定されている場合、GETまたはSETのレスポンスではサイトリターゲティングの設定リストは空で返ります。<br>
　※レスポンスは空で返りますが、実際のサイトリターゲティングの設定情報には「配信除外のターゲットリスト」は設定されています。</p></td>
    <td><p>■APIIF変更あり<br>
・“SiteRetargetingTarget”（サイトリターゲティングの設定を保持するオブジェクト）に”targetListDeliverType”（ターゲットリスト種別）のEntityを追加しました。（種別は「配信対象」と「配信除外」））</p></td>
  </tr>
  <tr>
    <td><p>AdGroupAdService</p></td>
    <td><p>■APIIF変更なし<br></p></td>
    <td><p>■APIIF変更あり<br>
・新規広告タイプ（レスポンシブ、広告枠サイズ固定）の情報を保持するオブジェクト”ResponsiveAd”と”StaticFrameAd”を追加しました。<br>
・“AdType”（広告タイプ）に”RESPONSIVE_AD”（レスポンシブ）と”STATIC_FRAME_AD”（広告枠サイズ固定）のEnum定義を追加しました。<br>
・“AdLayout”（広告レイアウト）のEnum定義を追加しました。<br>
・“ButtonText”（ボタンテキスト）のEnum定義を追加しました。<br>
<br>
■エラーコード<br>
・広告タイプと広告レイアウトの組み合わせが正しくない場合には「220126：Invalid pattern in ad type and layout.」を返します。<br>
・ボタンテキストを設定、追加する際に、ボタンテキストを設定、追加できない広告タイプまたは広告レイアウトの場合には「220127：Invalid ad type.」を返します。<br>
・カラーセットIDの指定が正しくない場合には「220128：Invalid colorSetId.」を返します。</p></td>
  </tr>
  <tr>
    <td><p>BulkService</p></td>
    <td><p>■APIIF変更なし<br>
・Bulkシートの変更を行いました。<br>
※変更点はVer.5.0と同様</p></td>
    <td><p>■APIIF変更なし<br>
・Bulkシートの変更を行いました。<br>
　※以下の項目を追加しました。<br>
　「ボタンテキスト」<br>
　「主体者表記」<br>
　「カラーセット」<br>
　「ロゴ画像ID」<br>
・新規広告タイプおよび広告レイアウトの入稿、出力を可能にしました。<br>
・「ターゲティングの種類」に「サイトリターゲティング（配信）」と「サイトリターゲティング（除外）」の2種類の設定を可能にしました。<br>
　※入稿、出力時に「サイトリターゲティング」の項目名を使用した場合、「サイトリターゲティング（配信）」として処理されます。</p></td>
  </tr>
  <tr>
    <td><p>RetargetingListService</p></td>
    <td><p>■APIIF変更なし<br>
■エラーコード<br>
ターゲットリストの作成上限に達しているため、それ以上ターゲットリストを追加できない場合には「120023：Over limit.」を返します。</p></td>
    <td><p>■APIIF変更あり。<br>
・ターゲットリストの上限数を1アカウントあたり300個に変更しました。<br>
・リターゲティングの条件を保持するオブジェクト” RuleCondition”に” type”（ルールの種類）を追加しました。<br>
・“RuleType”（条件種別）に”REFERER_URL”（リファラURL）のEnum定義を追加しました。</p></td>
  </tr>
  <tr>
    <td><p>MediaService</p></td>
    <td><p>■APIIF変更なし</p></td>
    <td><p>■APIIF変更あり<br>
・“ImageMedia”（画像設定内容を保持するオブジェクト）の”mediaAdFormat”（画像広告タイプ）をenum型からstring型に変更しました。<br>
・“MediaRecord”（ 画像情報を保持するオブジェクト）に”logoFlg” （ロゴ画像フラグ）を追加しました。<br>
※デフォルトは”FALSE”になります。<br>
<br>
■エラーコード<br>
・配信フラグとロゴフラグの組み合わせが正しくない場合には「220129：Invalid combination in user status and logo flag.」を返します。<br>
・ロゴフラグと画像フォーマットの組み合わせが正しくない場合には「220130：Invalid combination in logo flag and media format.」を返します。<br>
・更新できない項目の指定がある場合には「220131：Field value is not updatable.」を返します。</p></td>
  </tr>
  <tr>
    <td><p>DictionaryService</p></td>
    <td><p>■APIIF変更なし</p></td>
    <td><p>■APIIF変更あり<br>
・広告レイアウトのテーマ設定を取得する操作である“getColorSet”を追加しました。</p></td>
  </tr>
  <tr>
    <td><p>PlacementUrlIdeaService</p></td>
    <td><p>■APIIF変更なし</p></td>
    <td><p>■APIIF変更あり<br>
・“PlacementUrlIdeaSelector”（ getメソッドの検索条件を保持するオブジェクト）に以下の変更を行いました。<br>
　・”conditions”（検索キーワードとカテゴリー情報）を削除しました。<br>
　・”keyword”（URLを検索するためのキーワード情報）を追加しました。<br>
　・”siteCategories”（URLのカテゴリー情報）を追加しました。<br>
　・”adFormats”（広告掲載フォーマット）を追加しました。<br>
・広告掲載フォーマットの情報を保持するオブジェクト“adFormats”を追加しました。<br>
・カラー設定先の要素を表すEnum定義” ColorElement”を追加しました。</p></td>
  </tr>
</tbody></table>
