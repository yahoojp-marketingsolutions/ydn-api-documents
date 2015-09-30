# Release Notes
## Release version　　
5.0 (WSDL version: 5.0.0)
## Type of Version up　　
Major version up 
## Main Contents of this Release
#### 1. Site Retargeting Enhancement 
Functions are added and changed for Site Retargeting.  
  
*Maximum number of Target list setting is changed (300 lists per account).  
*Exclusion list setting is added (Exclusion list will be prioritized if both Target and Exclude are set).   
*Refer URL setting is added for Target list condition.  
*Maximum URL character is changed for Target list condition (250 byte).   
  
* Target Web Service  
 * [AdGroupTargetService](/docs/en/api_reference/services/AdGroupTargetService.md)
 * [RetargetingListService](/docs/en/api_reference/services/RetargetingListService.md)
  
* Target Data Object  
 * [SiteRetargetingTarget](/docs/en/api_reference/data/SiteRetargetingTarget.md)
 * [RuleCondition](/docs/en/api_reference/data/RuleCondition.md)
  
* Target Enumerations  
 * [TargetListDeliverType](/docs/en/api_reference/data/TargetListDeliverType.md)
 * [RuleType](/docs/en/api_reference/data/RuleType.md)
 
#### 2. New types of ads  
Two types of ads are added for the support of multi devices and ad display.<br>  
・RESPONSIVE_AD (Responsive) <br>
・STATIC_FRAME_AD (Static Frame) <br>
<br>
* Targeting setting is possible, excluding Site Category and Placement Targeting.<br>
* Image size will be adjusted (or cropped) to fit the frame. <br>
* Image will be cropped to fit the frame for RESPONSIVE_AD.<br>
* Submission rules for RESPONSIVE_AD are as follows.<br>
　・Title: 25 characters (Required)<br>
　・Description: 90 characters (Required)<br>
　・Display URL: 4-50 characters (Required)<br>
　・Destination URL: 11-1024 characters (Required)<br>
　・Image: 300 x 300, 1200 x 628* (Required)<br>
　*Currently, 1200 x 628 is not available for “Template”. Please wait for more details. <br> 
・Advertiser Indication: 20 characters (Required)<br>
・Text for button (Optional)<br>
・Logo image: 180 x 180 (Optional)<br>
<br>
*Can use three types of ad layout for STATIC_FRAME_AD.<br> 
<br>
<table class="standard">
  <tbody><tr>
    <th>Layout</th>
    <th>Details</th>
  </tr>
  <tr>
    <td>SQUARE_BANNER_TOP</td>
    <td>・Title: 15 characters (Required)<br>
・Description: none<br>
・Display URL: 4-29 characters (Required)<br>
・Destination URL: 11-1024 characters (Required)<br>
・Image: 300 x 300 (Required)<br>
・Advertiser Indication: 20 characters (Required)<br>
・Button (Optional)<br>
・Logo: 180 x 180 (Optional)<br>
・Color theme (Optional)</td>
  </tr>
  <tr>
    <td>WIDE_BANNER_TOP</td>
    <td>・Title: 20 characters (Required)<br>
・Description: 38 characters (Required)<br>
・Display URL: 4-29 characters (Required)<br>
・Destination URL: 11-1024 characters (Required)<br>
・Image: 1200 x 628 (Required)<br>
・Advertiser Indication: 20 characters (Required)<br>
・Logo: 180 x 180 (Optional)<br>
・Color theme (Optional)</td>
  </tr>
  <tr>
    <td>WIDE_BANNER_MIDDLE</td>
    <td>・Title: 20 characters (Required)<br>
・Description: 25 characters (Required)<br>
・Display URL: 4-29 characters (Required)<br>
・Destination URL: 11-1024 characters (Required)<br>
・Image: 300 x 300 (Required)<br>
・Advertiser Indication: 20 characters (Required)<br>
・Button (Optional)<br>
・Logo: 180 x 180 (Optional)<br>
・Color theme (Optional)</td>
  </tr>
</tbody></table>
  
* Target Web Service  
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
 * [MediaService](/docs/en/api_reference/services/MediaService.md)
 * [DictionaryService](/docs/en/api_reference/services/DictionaryService.md)
 * [PlacementUrlIdeaService](/docs/en/api_reference/services/PlacementUrlIdeaService.md)
  
* Target Data Object  
 * [AdGroupAd](/docs/en/api_reference/data/AdGroupAd.md)
 * [ResponsiveAd](/docs/en/api_reference/data/ResponsiveAd.md)
 * [StaticFrameAd](/docs/en/api_reference/data/StaticFrameAd.md)
 * [MediaRecord](/docs/en/api_reference/data/MediaRecord.md)
 * [ImageMedia](/docs/en/api_reference/data/ImageMedia.md)
 * [ColorSetSelector](/docs/en/api_reference/data/ColorSetSelector.md)
 * [ColorSetPage](/docs/en/api_reference/data/ColorSetPage.md)
 * [ColorSetValues](/docs/en/api_reference/data/ColorSetValues.md)
 * [ColorSet](/docs/en/api_reference/data/ColorSet.md)
 * [PlacementUrlIdeaSelector](/docs/en/api_reference/data/PlacementUrlIdeaSelector.md)
 * [AdFormatConditions](/docs/en/api_reference/data/AdFormatConditions.md)
  
* Target Enumerations  
 * [AdType](/docs/en/api_reference/data/AdType.md)
 * [AdLayout](/docs/en/api_reference/data/AdLayout.md)
 * [ButtonText](/docs/en/api_reference/data/ButtonText.md)
 * [LogoFlg](/docs/en/api_reference/data/LogoFlg.md)
 * [ColorElement](/docs/en/api_reference/data/ColorElement.md)

#### 3. Influence on each Versions by Service Change  
<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.4.7 and before</p></th>
    <th valign="top"><p>Ver.5.0</p></th>
  </tr>
  <tr>
    <td valign="top"><p>AdGroupTargetService</p></td>
    <td valign="top"><p>■No change in APIIF<br>
・If only one “Exclude” of Target list is set on Site Retargeting, the response of get and//or mutate(SET) of the list will be blank.<br>
*Response will be blank, but the actual “Exclude” Target list will be set. </p></td>
    <td valign="top"><p>■APIIF changed<br>
・Added “targetListDeliverType” entity on “SiteRetargetingTarget”.</p></td>
  </tr>
  <tr>
    <td valign="top"><p>AdGroupAdService</p></td>
    <td valign="top"><p>■No change on APIIF<br></p></td>
    <td valign="top"><p>■APIIF changed<br>
・Added “ResponsiveAd” and “StaticFrameAd”<br>
・Added enum of “RESPONSIVE_AD” and “STATIC_FRAME_AD” in “AdType”<br>
・Added enum in “AdLayout”<br>
・Added enum in “ButonText”<br>
<br>
■Error codes<br>
・“220126: Invalid pattern in ad type and layout.” will return if the Ad Type and Ad layout does not match.<br>
・“220127: Invalid ad type.” will return if Ad Type or Ad Layout is not the type that cannot be added or set to the Button text.<br>
・“220128: Invalid colorSetId.” will return if the Color Set ID is not correct.</p></td>
  </tr>
  <tr>
    <td valign="top"><p>BulkService</p></td>
    <td valign="top"><p>■No change on APIIF<br>
・Bulk sheet has been changed.<br>
　*Change elements are same as Ver.5.0</p></td>
    <td valign="top"><p>■No change on APIIF<br>
・Bulk sheet has been changed.<br>
　*Items below are added<br>
　- “Button Text”<br>
　- “Advertiser Indication”<br>
　- “Color Set”<br>
　- “Logo image ID”<br>
・Submit and display of new Ad Type and Ad Layout are possible.<br>
・Setting of “Target” and “Exclude” is possible from “Site Retargeting type”.<br>
　*If “Site Retargeting” is chosen in submit or display(get), it will return as “Target” setting.</p></td>
  </tr>
  <tr>
    <td valign="top"><p>RetargetingListService</p></td>
    <td valign="top"><p>■No change in APIIF<br>
■Error codes<br>
・“120023：Over limit.” will return if the Target list is over the limit.</p></td>
    <td valign="top"><p>■APIIF changed<br>
・Target list maximum is raised to 300 per account.<br>
・Added “type” (Rule type) in “RuleConditon”.<br>
・Added enum “REFERER_URL” in “RuleType”.</p></td>
  </tr>
  <tr>
    <td valign="top"><p>MediaService</p></td>
    <td valign="top"><p>■No change in APIIF</p></td>
    <td valign="top"><p>■APIIF changed<br>
・“mediaAdFormat” in “ImageMedia” has been changed to string data type.<br>
・“logoFlg” has been added on “MediaRecord”<br>
　*Default will be “FALSE”<br>
<br>
■Error codes<br>
・“220129: Invalid combination in user status and logo flag.” will return if combination of status and logo flag does not match.<br>
・“220130: Invalid combination in logo flag and media format.” will return if combination of Logo and Image format does not match.<br>
・“220131: Field value is not updatable.” will return if field value is chosen that is not updatable.</p></td>
  </tr>
  <tr>
    <td valign="top"><p>DictionaryService</p></td>
    <td valign="top"><p>■No change in APIIF</p></td>
    <td valign="top"><p>■APIIF changed<br>
・“getColorSet” is added to obtain the color set for Ad Layout.</p></td>
  </tr>
  <tr>
    <td valign="top"><p>PlacementUrlIdeaService</p></td>
    <td valign="top"><p>■No change in APIIF</p></td>
    <td valign="top"><p>■APIIF changed<br>
・Multiple changes been made for “PlacementUrlIdeaSelector”<br>
　・“conditions”is deleted.<br>
　・“keyword”is added.<br>
　・“siteCategories”is added.<br>
　・“adFormats”is added. <br>
・“adFormats”is added for Ad Distribution format information<br>
・“ColorElement”enum is added to set the element of color.</p></td>
  </tr>
</tbody></table>
