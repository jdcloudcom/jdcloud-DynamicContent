# deleteLiveStreamDomainRecord


## Description
Delete domain record configuration

## Request Method
DELETE

## Request Address
https://live.jdcloud-api.com/v1/recordDomains/{publishDomain}/templates/{template}

|Name|Type|Required or Not|Default Value|Description|
|---|---|---|---|---|
|**publishDomain**|String|True| |Pushing Streaming Accelerated Domain|
|**template**|String|True| |Record Template Customized Name|

## Request Parameter
None


## Return Parameter
|Name|Type|Description|
|---|---|---|
|**requestId**|String|ruquestId|


## Return Code
|Return Code|Description|
|---|---|
|**400**|Invalid parameter|
|**401**|Authentication failed|
|**404**|Not found|
|**503**|Service unavailable|
|**200**|OK|
|**500**|Internal server error|