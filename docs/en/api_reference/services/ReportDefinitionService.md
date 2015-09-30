# ReportDefinitionService
Use this service to get or add report definition. <br>
Report defines report type, date range, and fields. <br>
It provides operation to get available report fields for specific report type.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.0/ReportDefinitionService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.0/ReportDefinitionService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Retrieves and adds report definitions.<br>
If registered as template: The maximum of setting definition is 30.<br>
If not registered as template: There is no limit in setting definition.<br>
<br>
[Notes]<br>
Report definition can be confirmed only by the authentic method when the report definition was created.<br>
 - If it was created by authentication: Cannot confirm by on behalf of access.<br>
 - If it was created by on behalf of access: Cannot confirm by authentication.<br>
The maximum template is 30 entries per authentic method.<br>
<br>
The following ENUM are added to segment, to create a report divided by attribute per ad group.<br>
- SEARCH_KEYWORD<br>
- AGE<br>
- GENDER<br>
- LOCATION<br>
- SITE_CATEGORY<br>
- INTEREST_CATEGORY<br>
- AD_STYLE<br>

#### Operation
Describes operations provided by ReportDefinitionService.

## get
### Request
Retrieves the report definition.

| Parameter | Req? | Value | Description | 
|---|---|---|---|
| selector | ○ | [ReportDefinitionSelector](../data/ReportDefinitionSelector.md) | Report definition for the target of the operation. |

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:reportIds>9000000001</ns1:reportIds>
                <ns1:reportIds>9000000002</ns1:reportIds>               
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>  
                <ns1:reportIds>9000000001</ns1:reportIds>
                <ns1:reportIds>9000000002</ns1:reportIds>               
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription | 
|---|---|---|
| rval | [ReportDefinitionPage](../data/ReportDefinitionPage.md) | Entry of report definition. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>1</ns1:totalNumEntries>
                <ns1:Page.Type>ReportDefinitionPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDefinition>
                        <ns1:reportId>9000000001</ns1:reportId>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                        <ns1:reportType>ACCOUNT</ns1:reportType>
                        <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
                        <ns1:sort>+DAY</ns1:sort>
                        <ns1:segments>DAY</ns1:segments>
                        <ns1:segments>DELIVER</ns1:segments>
                        <ns1:segments>CONVERSION_NAME</ns1:segments>
                        <ns1:segments>OBJECTIVE_OF_CONVERSION_TRACKING</ns1:segments>
                        <ns1:fields>ACCOUNTNAME</ns1:fields>
                        <ns1:fields>ACCOUNTID</ns1:fields>
                        <ns1:fields>DAY</ns1:fields>
                        <ns1:fields>DELIVER</ns1:fields>
                        <ns1:fields>DEVICE</ns1:fields>
                        <ns1:fields>CONVERSIONNAME</ns1:fields>
                        <ns1:fields>OBJECTIVEOFCONVERSIONTRACKING</ns1:fields>
                        <ns1:fields>IMPRESSIONS</ns1:fields>
                        <ns1:fields>CLICKS</ns1:fields>
                        <ns1:fields>CTR</ns1:fields>
                        <ns1:fields>AVERAGEPOSITION</ns1:fields>
                        <ns1:fields>COST</ns1:fields>
                        <ns1:fields>AVERAGECPC</ns1:fields>
                        <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                        <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                        <ns1:fields>TOTALREVENUE</ns1:fields>
                        <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
                        <ns1:fields>MEASURABLEIMPRESSIONS</ns1:fields>
                        <ns1:fields>VIEWABLEIMPRESSIONS</ns1:fields>
                        <ns1:fields>VIEWABLEIMPRESSIONRATE</ns1:fields>
                        <ns1:fields>VIEWABLECLICKS</ns1:fields>
                        <ns1:fields>VIEWABLECTR</ns1:fields>
                        <ns1:format>CSV</ns1:format>
                        <ns1:encode>UTF-8</ns1:encode>
                        <ns1:zip>ON</ns1:zip>
                        <ns1:lang>EN</ns1:lang>
                        <ns1:frequency>SPECIFYDAY</ns1:frequency>
                        <ns1:specifyDay>10</ns1:specifyDay>
                        <ns1:addTemplate>YES</ns1:addTemplate>
                    </ns1:reportDefinition>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (For Frequency)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>1</ns1:totalNumEntries>
                <ns1:Page.Type>ReportDefinitionPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDefinition>
                        <ns1:reportId>9000000001</ns1:reportId>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                        <ns1:reportType>FREQUENCY</ns1:reportType>
                        <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
                        <ns1:sort>+DAY</ns1:sort>
                        <ns1:segments>DAY</ns1:segments>
                        <ns1:fields>ACCOUNTNAME</ns1:fields>
                        <ns1:fields>ACCOUNTID</ns1:fields>
                        <ns1:fields>DAY</ns1:fields>
                        <ns1:fields>IMPRESSIONS</ns1:fields>
                        <ns1:fields>CLICKS</ns1:fields>
                        <ns1:fields>CTR</ns1:fields>
                        <ns1:fields>COST</ns1:fields>
                        <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                        <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                        <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                        <ns1:fields>FREQUENCY</ns1:fields>
                        <ns1:fields>REACH</ns1:fields>
                        <ns1:format>CSV</ns1:format>
                        <ns1:encode>UTF-8</ns1:encode>
                        <ns1:zip>ON</ns1:zip>
                        <ns1:lang>EN</ns1:lang>
                        <ns1:frequency>SPECIFYDAY</ns1:frequency>
                        <ns1:specifyDay>10</ns1:specifyDay>
                        <ns1:addTemplate>YES</ns1:addTemplate>
                    </ns1:reportDefinition>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getReportFields
### Request
Returns usable report fields by report type.

| Parameter | Req? | Value | Description | 
|---|---|---|---|
| accountId | ○ | xsd:long | Account ID |
|reportType | ○ | [enum ReportType](../data/enumReportType.md) | Report format. |
|lang |  | [enum ReportLang](../data/enumReportLang.md) | Output language.<br>Japanese or English can be selected. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getReportFields>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:reportType>ACCOUNT</ns1:reportType>
            <ns1:lang>JA</ns1:lang>
        </ns1:getReportFields>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>33333-3333-33333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getReportFields>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:reportType>ACCOUNT</ns1:reportType>
            <ns1:lang>JA</ns1:lang>
        </ns1:getReportFields>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription | 
|---|---|---|
| rval | [ReportDefinitionFieldValue](../data/ReportDefinitionFieldValue.md) | Usable report entry to be acquired.
| error | [Error](../data/Error.md) | An error. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportDefinitionService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getReportFieldsResponse>
            <ns1:rval>
                <ns1:operationSucceeded>true</ns1:operationSucceeded>
                <ns1:field>
                    <ns1:fieldName>ACCOUNTID</ns1:fieldName>
                    <ns1:displayFieldName>Account ID</ns1:displayFieldName>
                    <ns1:xmlAttributeName>accountID</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>COSTTOTALCONVERSIONS</ns1:fieldName>
                    <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
                    <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
                </ns1:field>
            </ns1:rval>
        </ns1:getReportFieldsResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (For Frequency)
```xml															
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V4">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ReportDefinitionService</ns1:service>
      <ns1:remainingQuota>19997</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0131</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getReportFieldsResponse>
      <ns1:rval>
        <ns1:operationSucceeded>true</ns1:operationSucceeded>
        <ns1:field>
          <ns1:fieldName>ACCOUNTNAME</ns1:fieldName>
          <ns1:displayFieldName>Account Name</ns1:displayFieldName>
          <ns1:xmlAttributeName>accountName</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>ACCOUNTID</ns1:fieldName>
          <ns1:displayFieldName>Account ID</ns1:displayFieldName>
          <ns1:xmlAttributeName>accountID</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>CAMPAIGNNAME</ns1:fieldName>
          <ns1:displayFieldName>Campaign Name</ns1:displayFieldName>
          <ns1:xmlAttributeName>campaignName</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>CAMPAIGNID</ns1:fieldName>
          <ns1:displayFieldName>Campaign ID</ns1:displayFieldName>
          <ns1:xmlAttributeName>campaignID</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>ADGROUPNAME</ns1:fieldName>
          <ns1:displayFieldName>Ad Group Name</ns1:displayFieldName>
          <ns1:xmlAttributeName>adgroupName</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>ADGROUPID</ns1:fieldName>
          <ns1:displayFieldName>Ad Group ID</ns1:displayFieldName>
          <ns1:xmlAttributeName>adgroupID</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>ADNAME</ns1:fieldName>
          <ns1:displayFieldName>Ad Name</ns1:displayFieldName>
          <ns1:xmlAttributeName>adName</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>ADID</ns1:fieldName>
          <ns1:displayFieldName>Ad ID</ns1:displayFieldName>
          <ns1:xmlAttributeName>adID</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>ADSTYLE</ns1:fieldName>
          <ns1:displayFieldName>Ad Format (Media Type)</ns1:displayFieldName>
          <ns1:xmlAttributeName>adStyle</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>CONVERSIONNAME</ns1:fieldName>
          <ns1:displayFieldName>Impressions</ns1:displayFieldName>
          <ns1:xmlAttributeName>impressions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>OBJECTIVEOFCONVERSIONTRACKING</ns1:fieldName>
          <ns1:displayFieldName>Impressions</ns1:displayFieldName>
          <ns1:xmlAttributeName>impressions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>IMPRESSIONS</ns1:fieldName>
          <ns1:displayFieldName>Impressions</ns1:displayFieldName>
          <ns1:xmlAttributeName>impressions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>CLICKS</ns1:fieldName>
          <ns1:displayFieldName>Clicks</ns1:displayFieldName>
          <ns1:xmlAttributeName>clicks</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>CTR</ns1:fieldName>
          <ns1:displayFieldName>CTR</ns1:displayFieldName>
          <ns1:xmlAttributeName>ctr</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>COST</ns1:fieldName>
          <ns1:displayFieldName>Cost</ns1:displayFieldName>
          <ns1:xmlAttributeName>cost</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>AVERAGECPC</ns1:fieldName>
          <ns1:displayFieldName>Avg. CPC</ns1:displayFieldName>
          <ns1:xmlAttributeName>averageCpc</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>TOTALCONVERSIONS</ns1:fieldName>
          <ns1:displayFieldName>Total Conversions</ns1:displayFieldName>
          <ns1:xmlAttributeName>totalConversions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>TOTALCONVERSIONRATE</ns1:fieldName>
          <ns1:displayFieldName>Total Conversion Rate</ns1:displayFieldName>
          <ns1:xmlAttributeName>totalConversionRate</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>COSTTOTALCONVERSIONS</ns1:fieldName>
          <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
          <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>TOTALREVENUE</ns1:fieldName>
          <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
          <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>REVENUETOTALCONVERSIONS</ns1:fieldName>
          <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
          <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>MEASURABLEIMPRESSIONS</ns1:fieldName>
          <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
          <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>VIEWABLEIMPRESSIONS</ns1:fieldName>
          <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
          <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>VIEWABLEIMPRESSIONRATE</ns1:fieldName>
          <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
          <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>VIEWABLECLICKS</ns1:fieldName>
          <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
          <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>VIEWABLECTR</ns1:fieldName>
          <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
          <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>FREQUENCY</ns1:fieldName>
          <ns1:displayFieldName>Frequency</ns1:displayFieldName>
          <ns1:xmlAttributeName>frequency</ns1:xmlAttributeName>
        </ns1:field>
        <ns1:field>
          <ns1:fieldName>REACH</ns1:fieldName>
          <ns1:displayFieldName>Reach</ns1:displayFieldName>
          <ns1:xmlAttributeName>reach</ns1:xmlAttributeName>
        </ns1:field>
      </ns1:rval>
    </ns1:getReportFieldsResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```															

## mutate(ADD)
### Request
Adds report definitions.

| Parameter | Req? | Value | Description | 
|---|---|---|---|
| operations | ○ | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md)|Displays operation target report definitions and operation content. | 

##### Request Sample (For AdHoc Report)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                    <ns1:reportType>ACCOUNT</ns1:reportType>
                    <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                    <ns1:dateRange>
                        <ns1:startDate>20120303</ns1:startDate>
                        <ns1:endDate>20120402</ns1:endDate>
                    </ns1:dateRange>
                    <ns1:sort>+DAY</ns1:sort>
                    <ns1:segments>DAY</ns1:segments>
                    <ns1:segments>DELIVER</ns1:segments>
                    <ns1:segments>DEVICE_AND_CARRIER</ns1:segments>
                    <ns1:segments>CONVERSION_NAME</ns1:segments>
                    <ns1:segments>OBJECTIVE_OF_CONVERSION_TRACKING</ns1:segments>
                    <ns1:fields>ACCOUNTNAME</ns1:fields>
                    <ns1:fields>ACCOUNTID</ns1:fields>
                    <ns1:fields>DAY</ns1:fields>
                    <ns1:fields>DELIVER</ns1:fields>
                    <ns1:fields>DEVICE</ns1:fields>
                    <ns1:fields>CONVERSIONNAME</ns1:fields>
                    <ns1:fields>OBJECTIVEOFCONVERSIONTRACKING</ns1:fields>
                    <ns1:fields>IMPRESSIONS</ns1:fields>
                    <ns1:fields>CLICKS</ns1:fields>
                    <ns1:fields>CTR</ns1:fields>
                    <ns1:fields>AVERAGEPOSITION</ns1:fields>
                    <ns1:fields>COST</ns1:fields>
                    <ns1:fields>AVERAGECPC</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                    <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                    <ns1:fields>TOTALREVENUE</ns1:fields>
                    <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
                    <ns1:fields>MEASURABLEIMPRESSIONS</ns1:fields>
                    <ns1:fields>VIEWABLEIMPRESSIONS</ns1:fields>
                    <ns1:fields>VIEWABLEIMPRESSIONRATE</ns1:fields>
                    <ns1:fields>VIEWABLECLICKS</ns1:fields>
                    <ns1:fields>VIEWABLECTR</ns1:fields>
                    <ns1:format>CSV</ns1:format>
                    <ns1:encode>UTF-8</ns1:encode>
                    <ns1:zip>ON</ns1:zip>
                    <ns1:lang>EN</ns1:lang>
                    <ns1:addTemplate>NO</ns1:addTemplate>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (For Scheduled Report)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                    <ns1:reportType>ACCOUNT</ns1:reportType>
                    <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
                    <ns1:sort>+DAY</ns1:sort>
                    <ns1:segments>DAY</ns1:segments>
                    <ns1:segments>DELIVER</ns1:segments>
                    <ns1:segments>DEVICE_AND_CARRIER</ns1:segments>
                    <ns1:segments>CONVERSION_NAME</ns1:segments>
                    <ns1:segments>OBJECTIVE_OF_CONVERSION_TRACKING</ns1:segments>
                    <ns1:fields>ACCOUNTNAME</ns1:fields>
                    <ns1:fields>ACCOUNTID</ns1:fields>
                    <ns1:fields>DAY</ns1:fields>
                    <ns1:fields>DELIVER</ns1:fields>
                    <ns1:fields>DEVICE</ns1:fields>
                    <ns1:fields>CONVERSIONNAME</ns1:fields>
                    <ns1:fields>OBJECTIVEOFCONVERSIONTRACKING</ns1:fields>
                    <ns1:fields>IMPRESSIONS</ns1:fields>
                    <ns1:fields>CLICKS</ns1:fields>
                    <ns1:fields>CTR</ns1:fields>
                    <ns1:fields>AVERAGEPOSITION</ns1:fields>
                    <ns1:fields>COST</ns1:fields>
                    <ns1:fields>AVERAGECPC</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                    <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                    <ns1:fields>TOTALREVENUE</ns1:fields>
                    <ns1:fields>REVENUETOTALCONVERSION</ns1:fields>
                    <ns1:fields>MEASURABLEIMPRESSION</ns1:fields>
                    <ns1:fields>VIEWABLEIMPRESSIONS</ns1:fields>
                    <ns1:fields>VIEWABLEIMPRESSIONRATE</ns1:fields>
                    <ns1:fields>VIEWABLECLICKS</ns1:fields>
                    <ns1:fields>VIEWABLECTR</ns1:fields>
                    <ns1:format>CSV</ns1:format>
                    <ns1:encode>UTF-8</ns1:encode>
                    <ns1:zip>ON</ns1:zip>
                    <ns1:lang>EN</ns1:lang>
                    <ns1:frequency>SPECIFYDAY</ns1:frequency>
                    <ns1:specifyDay>10</ns1:specifyDay>
                    <ns1:addTemplate>YES</ns1:addTemplate>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                    <ns1:reportType>ACCOUNT</ns1:reportType>
                    <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>                   
                    <ns1:sort>+DAY</ns1:sort>
                    <ns1:segments>DAY</ns1:segments>
                    <ns1:segments>DELIVER</ns1:segments>
                    <ns1:segments>DEVICE_AND_CARRIER</ns1:segments>
                    <ns1:segments>CONVERSION_NAME</ns1:segments>
                    <ns1:segments>OBJECTIVE_OF_CONVERSION_TRACKING</ns1:segments>
                    <ns1:fields>ACCOUNTNAME</ns1:fields>
                    <ns1:fields>ACCOUNTID</ns1:fields>
                    <ns1:fields>DAY</ns1:fields>
                    <ns1:fields>DELIVER</ns1:fields>
                    <ns1:fields>DEVICE</ns1:fields>
                    <ns1:fields>CONVERSIONNAME</ns1:fields>
                    <ns1:fields>OBJECTIVEOFCONVERSIONTRACKING</ns1:fields>
                    <ns1:fields>IMPRESSIONS</ns1:fields>
                    <ns1:fields>CLICKS</ns1:fields>
                    <ns1:fields>CTR</ns1:fields>
                    <ns1:fields>AVERAGEPOSITION</ns1:fields>
                    <ns1:fields>COST</ns1:fields>
                    <ns1:fields>AVERAGECPC</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                    <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                    <ns1:fields>TOTALREVENUE</ns1:fields>
                    <ns1:fields>REVENUETOTALCONVERSION</ns1:fields>
                    <ns1:fields>MEASURABLEIMPRESSION</ns1:fields>
                    <ns1:fields>VIEWABLEIMPRESSIONS</ns1:fields>
                    <ns1:fields>VIEWABLEIMPRESSIONRATE</ns1:fields>
                    <ns1:fields>VIEWABLECLICKS</ns1:fields>
                    <ns1:fields>VIEWABLECTR</ns1:fields>
                    <ns1:format>CSV</ns1:format>
                    <ns1:encode>UTF-8</ns1:encode>
                    <ns1:zip>ON</ns1:zip>
                    <ns1:lang>EN</ns1:lang>
                    <ns1:frequency>SPECIFYDAY</ns1:frequency>
                    <ns1:specifyDay>10</ns1:specifyDay>
                    <ns1:addTemplate>YES</ns1:addTemplate>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container holding report definitions, including operation results. |
| error | [Error](../data/Error.md) | An error. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportDefinitionService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDefinition>
                        <ns1:reportId>9000000001</ns1:reportId>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                        <ns1:reportType>ACCOUNT</ns1:reportType>
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                        <ns1:sort>+DAY</ns1:sort>
                        <ns1:segments>DAY</ns1:segments>
                        <ns1:segments>DELIVER</ns1:segments>
                        <ns1:segments>DEVICE_AND_CARRIER</ns1:segments>
                        <ns1:segments>CONVERSION_NAME</ns1:segments>
                        <ns1:segments>OBJECTIVE_OF_CONVERSION_TRACKING</ns1:segments>
                        <ns1:fields>ACCOUNTNAME</ns1:fields>
                        <ns1:fields>ACCOUNTID</ns1:fields>
                        <ns1:fields>DAY</ns1:fields>
                        <ns1:fields>DELIVER</ns1:fields>
                        <ns1:fields>DEVICE</ns1:fields>
                        <ns1:fields>CONVERSIONNAME</ns1:fields>
                        <ns1:fields>OBJECTIVEOFCONVERSIONTRACKING</ns1:fields>
                        <ns1:fields>IMPRESSIONS</ns1:fields>
                        <ns1:fields>CLICKS</ns1:fields>
                        <ns1:fields>CTR</ns1:fields>
                        <ns1:fields>AVERAGEPOSITION</ns1:fields>
                        <ns1:fields>COST</ns1:fields>
                        <ns1:fields>AVERAGECPC</ns1:fields>
                        <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                        <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                        <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                        <ns1:fields>TOTALREVENUE</ns1:fields>
                        <ns1:fields>REVENUETOTALCONVERSION</ns1:fields>
                        <ns1:fields>MEASURABLEIMPRESSION</ns1:fields>
                        <ns1:fields>VIEWABLEIMPRESSIONS</ns1:fields>
                        <ns1:fields>VIEWABLEIMPRESSIONRATE</ns1:fields>
                        <ns1:fields>VIEWABLECLICKS</ns1:fields>
                        <ns1:fields>VIEWABLECTR</ns1:fields>
                        <ns1:format>CSV</ns1:format>
                        <ns1:encode>UTF-8</ns1:encode>
                        <ns1:zip>ON</ns1:zip>
                        <ns1:lang>EN</ns1:lang>
                        <ns1:frequency>SPECIFYDAY</ns1:frequency>
                        <ns1:specifyDay>10</ns1:specifyDay>
                        <ns1:addTemplate>YES</ns1:addTemplate>
                    </ns1:reportDefinition>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### Request
Upgrade the report definition.

| Parameter | Req? | Value | Description | 
|---|---|---|---|
| operations | ○ | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md)|Displays operation target report definitions and operation content. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:reportId>1000000001</ns1:reportId>
                    <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                    <ns1:frequency>SPECIFYDAY</ns1:frequency>
                    <ns1:specifyDay>10</ns1:specifyDay>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:reportId>1000000001</ns1:reportId>
                    <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                    <ns1:frequency>SPECIFYDAY</ns1:frequency>
                    <ns1:specifyDay>10</ns1:specifyDay>               
　　　　　　　    </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container of report definition including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportDefinitionService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDefinition>
                        <ns1:reportId>9000000001</ns1:reportId>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                        <ns1:reportType>ACCOUNT</ns1:reportType>
                        <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
                        <ns1:sort>+DAY</ns1:sort>
                        <ns1:segments>DAY</ns1:segments>
                        <ns1:segments>DELIVER</ns1:segments>
                        <ns1:segments>DEVICE_AND_CARRIER</ns1:segments>
                        <ns1:segments>CONVERSION_NAME</ns1:segments>
                        <ns1:segments>OBJECTIVE_OF_CONVERSION_TRACKING</ns1:segments>
                        <ns1:fields>ACCOUNTNAME</ns1:fields>
                        <ns1:fields>ACCOUNTID</ns1:fields>
                        <ns1:fields>DAY</ns1:fields>
                        <ns1:fields>DELIVER</ns1:fields>
                        <ns1:fields>DEVICE</ns1:fields>
                        <ns1:fields>CONVERSIONNAME</ns1:fields>
                        <ns1:fields>OBJECTIVEOFCONVERSIONTRACKING</ns1:fields>
                        <ns1:fields>IMPRESSIONS</ns1:fields>
                        <ns1:fields>CLICKS</ns1:fields>
                        <ns1:fields>CTR</ns1:fields>
                        <ns1:fields>AVERAGEPOSITION</ns1:fields>
                        <ns1:fields>COST</ns1:fields>
                        <ns1:fields>AVERAGECPC</ns1:fields>
                        <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                        <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                        <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                        <ns1:fields>TOTALREVENUE</ns1:fields>
                        <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
                        <ns1:fields>MEASURABLEIMPRESSIONS</ns1:fields>
                        <ns1:fields>VIEWABLEIMPRESSIONS</ns1:fields>
                        <ns1:fields>VIEWABLEIMPRESSIONRATE</ns1:fields>
                        <ns1:fields>VIEWABLECLICKS</ns1:fields>
                        <ns1:fields>VIEWABLECTR</ns1:fields>
                        <ns1:format>CSV</ns1:format>
                        <ns1:encode>UTF-8</ns1:encode>
                        <ns1:zip>ON</ns1:zip>
                        <ns1:lang>EN</ns1:lang>
                        <ns1:frequency>SPECIFYDAY</ns1:frequency>
                        <ns1:specifyDay>10</ns1:specifyDay>
                        <ns1:addTemplate>YES</ns1:addTemplate>
                    </ns1:reportDefinition>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### Request
Deletes the report definition.。

| Parameter | Req? | Value | Description | 
|---|---|---|---|
| operations | ○ | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) |Report definition or operation elements of target of the operation. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:reportId>1000000001</ns1:reportId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:reportId>1000000001</ns1:reportId>             
　　　　　　　    </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container of report definition including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportDefinitionService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDefinition>
                        <ns1:reportId>9000000001</ns1:reportId>
                    </ns1:reportDefinition>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
