# modifyLiveDomainForwardCustomVhost


## Description
Set forward pushing domain

## Request Method
POST

## Request Address
https://cdn.jdcloud-api.com/v1/liveDomain/{domain}:putForwardCustomVhost

|Name|Type|Required or Not|Default Value|Description|
|---|---|---|---|---|
|**domain**|String|True| |User Domain|

## Request Parameter
|Name|Type|Required or Not|Default Value|Description|
|---|---|---|---|---|
|**forwardCustomVhost**|String|True| |Forward Pushing Domain|


## Return Parameter
|Name|Type|Description|
|---|---|---|
|**result**|Object| |
|**requestId**|String| |


## Return Code
|Return Code|Description|
|---|---|
|**200**|OK|
|**404**|NOT_FOUND|
