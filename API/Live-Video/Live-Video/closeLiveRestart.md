# closeLiveRestart


## Description
Close restart

## Request Method
PUT

## Request Address
https://live.jdcloud-api.com/v1/liveRestart:close


## Request Parameter
|Name|Type|Required or Not|Default Value|Description|
|---|---|---|---|---|
|**restartDomain**|String|True| |Playing Domain for Restarting|


## Response parameter
|Name|Type|Description|
|---|---|---|
|**requestId**|String|requestId|


## Return Code
|Return Code|Description|
|---|---|
|**200**|OK|
|**400**|Invalid parameter|
|**401**|Authentication failed|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|
