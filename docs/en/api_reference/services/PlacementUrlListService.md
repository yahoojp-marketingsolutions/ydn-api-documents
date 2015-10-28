# PlacementUrlListService
In PlacementUrlListService, acquiring, creating, updating and deleting Placement URL list will be done.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.0/PlacementUrlListService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.0/PlacementUrlListService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
In PlacementUrlListService, acquiring, creating, updating and deleting Placement URL list will be done.
#### Operation
Explains the control providing from PlacementUrlListService.
## get
### Request
Request Body’s Parameter

| name | type | Req? | Description | 
|---|---|---|---|
| selector | [PlacementUrlListSelector](../data/PlacementUrlListSelector.md) | Req |  | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
                <ns1:urlListIds>33333</ns1:urlListIds> 
                <ns1:urlListIds>22222</ns1:urlListIds>
                <ns1:urlListIds>11111</ns1:urlListIds> 
                <ns1:paging>
                   <ns1:startIndex>1</ns1:startIndex>
                   <ns1:numberResults>5</ns1:numberResults>
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
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
                <ns1:urlListIds>33333</ns1:urlListIds> 
                <ns1:urlListIds>22222</ns1:urlListIds>
                <ns1:urlListIds>11111</ns1:urlListIds>
                <ns1:paging>
                   <ns1:startIndex>1</ns1:startIndex>
                   <ns1:numberResults>5</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| name | type | Req? | Description | 
|---|---|---|---|
| rval | [PlacementUrlListPage](../data/PlacementUrlListPage.md) |  |  | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>PlacementUrlListService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:Page.Type>PlacementUrlListPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>33333</ns1:urlListId>
                        <ns1:urlListName>name3</ns1:urlListName>
                        <ns1:description>desc3</ns1:description>
                        <ns1:urls>
                            <ns1:placementUrl>sample3.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample33.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample333.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>PAUSED</ns1:activeFlg>
                        </ns1:urls>
                    </ns1:urlList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>22222</ns1:urlListId>
                        <ns1:urlListName>name2</ns1:urlListName>
                        <ns1:description>desc2</ns1:description>
                        <ns1:urls>
                            <ns1:placementUrl>sample2.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample22.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample222.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>PAUSED</ns1:activeFlg>
                        </ns1:urls>
                    </ns1:urlList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>11111</ns1:urlListId>
                        <ns1:urlListName>name1</ns1:urlListName>
                        <ns1:description>desc1</ns1:description>
                        <ns1:urls>
                            <ns1:placementUrl>sample1.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample11.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample111.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>PAUSED</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>UNKNOWN</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls> 
                    </ns1:urlList>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### Request
Request Body’s Parameter.

| name | type | Req? | Description | 
|---|---|---|---|
| perations | [PlacementUrlListOperation](../data/PlacementUrlListOperation.md) | req |  | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListName>name1</ns1:urlListName>
                    <ns1:description>desc1</ns1:description>
                    <ns1:urls>
                        <ns1:placementUrl>sample1.co.jp</ns1:placementUrl>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample11.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample111.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>PAUSED</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>UNKNOWN</ns1:placementUrl>
                    </ns1:urls> 
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListName>name2</ns1:urlListName>
                    <ns1:description>desc2</ns1:description>
                    <ns1:urls>
                        <ns1:placementUrl>sample2.co.jp</ns1:placementUrl>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample22.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample222.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>PAUSED</ns1:activeFlg>
                    </ns1:urls>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListName>name3</ns1:urlListName>
                    <ns1:description>desc3</ns1:description>
                    <ns1:urls>
                        <ns1:placementUrl>sample3.co.jp</ns1:placementUrl>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample33.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample333.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>PAUSED</ns1:activeFlg>
                    </ns1:urls>
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
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListName>name1</ns1:urlListName>
                    <ns1:description>desc1</ns1:description>
                    <ns1:urls>
                        <ns1:placementUrl>sample1.co.jp</ns1:placementUrl>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample11.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample111.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>PAUSED</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>UNKNOWN</ns1:placementUrl>
                    </ns1:urls> 
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListName>name2</ns1:urlListName>
                    <ns1:description>desc2</ns1:description>
                    <ns1:urls>
                        <ns1:placementUrl>sample2.co.jp</ns1:placementUrl>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample22.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample222.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>PAUSED</ns1:activeFlg>
                    </ns1:urls>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListName>name3</ns1:urlListName>
                    <ns1:description>desc3</ns1:description>
                    <ns1:urls>
                        <ns1:placementUrl>sample3.co.jp</ns1:placementUrl>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample33.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample333.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>PAUSED</ns1:activeFlg>
                    </ns1:urls>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| name | type | Req? | Description | 
|---|---|---|---|
| rval | [PlacementUrlListReturnValue](../data/PlacementUrlListReturnValue.md) |  |  | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>PlacementUrlListService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>PlacementUrlListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>33333</ns1:urlListId>
                        <ns1:urlListName>name3</ns1:urlListName>
                        <ns1:description>desc3</ns1:description>
                        <ns1:urls>
                            <ns1:placementUrl>sample3.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample33.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample333.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>PAUSED</ns1:activeFlg>
                        </ns1:urls>
                    </ns1:urlList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>22222</ns1:urlListId>
                        <ns1:urlListName>name2</ns1:urlListName>
                        <ns1:description>desc2</ns1:description>
                        <ns1:urls>
                            <ns1:placementUrl>sample2.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample22.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample222.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>PAUSED</ns1:activeFlg>
                        </ns1:urls>
                    </ns1:urlList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>11111</ns1:urlListId>
                        <ns1:urlListName>name1</ns1:urlListName>
                        <ns1:description>desc1</ns1:description>
                        <ns1:urls>
                            <ns1:placementUrl>sample1.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample11.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample111.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>PAUSED</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>UNKNOWN</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                    </ns1:urlList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### Request

| name | type | Req? | Description | 
|---|---|---|---|
| operations | [PlacementUrlListOperation](../data/PlacementUrlListOperation.md) | req |  | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>11111</ns1:urlListId>
                    <ns1:description>desc1_set</ns1:description>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>22222</ns1:urlListId>
                    <ns1:urls>
                        <ns1:placementUrl>sample2.co.jp</ns1:placementUrl>
                       <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample22.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample222.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>PAUSED</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>UNKNOWN</ns1:placementUrl>
                    </ns1:urls>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>33333</ns1:urlListId>
                    <ns1:urls>
                        <ns1:placementUrl>sample3333.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample33333.co.jp</ns1:placementUrl>
                    </ns1:urls> 
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
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>11111</ns1:urlListId>
                    <ns1:urlListName>name1_set</ns1:urlListName>
                    <ns1:description>desc1_set</ns1:description>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>22222</ns1:urlListId>
                    <ns1:urls>
                        <ns1:placementUrl>sample2.co.jp</ns1:placementUrl>
                       <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample22.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample222.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>PAUSED</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>UNKNOWN</ns1:placementUrl>
                    </ns1:urls>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>33333</ns1:urlListId>
                    <ns1:urls>
                        <ns1:placementUrl>sample3333.co.jp</ns1:placementUrl>
                        <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                    </ns1:urls>
                    <ns1:urls>
                        <ns1:placementUrl>sample33333.co.jp</ns1:placementUrl>
                    </ns1:urls>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| name | type | Req? | Description | 
|---|---|---|---|
| rval | [PlacementUrlListReturnValue](../data/PlacementUrlListReturnValue.md) |  |  | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>PlacementUrlListService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>PlacementUrlListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>33333</ns1:urlListId>
                        <ns1:urlListName>name3</ns1:urlListName>
                        <ns1:description>desc3</ns1:description>
                        <ns1:unknownDomain>EXCLUDE</ns1:unknownDomain>
                        <ns1:urls>
                            <ns1:placementUrl>sample3333.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample33333.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                    </ns1:urlList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>22222</ns1:urlListId>
                        <ns1:urlListName>name2</ns1:urlListName>
                        <ns1:description>desc2</ns1:description>
                        <ns1:unknownDomain>INCLUDE</ns1:unknownDomain>
                        <ns1:urls>
                            <ns1:placementUrl>sample2.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample22.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample222.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>PAUSED</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>UNKNOWN</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                    </ns1:urlList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>11111</ns1:urlListId>
                        <ns1:urlListName>name1_set</ns1:urlListName>
                        <ns1:description>desc1_set</ns1:description>
                        <ns1:unknownDomain>INCLUDE</ns1:unknownDomain>
                        <ns1:urls>
                            <ns1:placementUrl>sample1.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample11.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample111.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>PAUSED</ns1:activeFlg>
                        </ns1:urls>
                    </ns1:urlList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### Request

| name | type | Req? | Description | 
|---|---|---|---|
| operations | [PlacementUrlListOperation](../data/PlacementUrlListOperation.md) | req |  | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>11111</ns1:urlListId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>22222</ns1:urlListId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>33333</ns1:urlListId>
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
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>11111</ns1:urlListId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>22222</ns1:urlListId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:urlListId>33333</ns1:urlListId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| name | type | Req? | Description | 
|---|---|---|---|
| rval | [PlacementUrlListReturnValue](../data/PlacementUrlListReturnValue.md) |  |  | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>PlacementUrlListService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>PlacementUrlListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>33333</ns1:urlListId>
                        <ns1:urlListName>name3</ns1:urlListName>
                        <ns1:description>desc3</ns1:description>
                        <ns1:urls>
                            <ns1:placementUrl>sample3333.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample33333.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls> 
                    </ns1:urlList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>22222</ns1:urlListId>
                        <ns1:urlListName>name2</ns1:urlListName>
                        <ns1:description>desc2</ns1:description>
                        <ns1:unknownDomain>INCLUDE</ns1:unknownDomain>
                        <ns1:urls>
                            <ns1:placementUrl>sample2.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample22.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample222.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>PAUSED</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>UNKNOWN</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls> 
                    </ns1:urlList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:urlList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:urlListId>11111</ns1:urlListId>
                        <ns1:urlListName>name1_set</ns1:urlListName>
                        <ns1:description>desc1_set</ns1:description>
                        <ns1:unknownDomain>INCLUDE</ns1:unknownDomain>
                        <ns1:urls>
                            <ns1:placementUrl>sample1.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample11.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>sample111.co.jp</ns1:placementUrl>
                            <ns1:activeFlg>PAUSED</ns1:activeFlg>
                        </ns1:urls>
                        <ns1:urls>
                            <ns1:placementUrl>UNKNOWN</ns1:placementUrl>
                            <ns1:activeFlg>ACTIVE</ns1:activeFlg>
                        </ns1:urls>
                    </ns1:urlList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
