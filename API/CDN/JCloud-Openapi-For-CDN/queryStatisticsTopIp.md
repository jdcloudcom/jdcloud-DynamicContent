# queryStatisticsTopIp


## Description
Query TOP IP

## Request Method
POST

## Request Address
https://cdn.jdcloud-api.com/v1/statistics:topIp


## Request Parameter
|Name|Type|Required or Not|Default Value|Description|
|---|---|---|---|---|
|**startTime**|String|True| |Search start time, UTC time, format: yyyy-MM-dd'T'HH:mm:ss’Z’, example: 2018-10-21T10:00:00Z|
|**endTime**|String|True| |Search end time, UTC time, format: yyyy-MM-dd'T'HH:mm:ss’Z’, example: 2018-10-21T10:00:00Z|
|**domain**|String|False| |Domain required to be searched must be domain with permission under user pin|
|**subDomain**|String|False| |Subdomain To Be Searched|
|**size**|Integer|False|20| |
|**topBy**|String|False| |Sorting Basis|


## Return Parameter
|Name|Type|Description|
|---|---|---|
|**result**|[Result](querystatisticstopip#result)| |
|**requestId**|String| |

### <div id="result">Result</div>
|Name|Type|Description|
|---|---|---|
|**startTime**|String| |
|**endTime**|String| |
|**domain**|String| |
|**ipData**|[StatisticsTopIpData[]](querystatisticstopip#statisticstopipdata)| |
### <div id="statisticstopipdata">StatisticsTopIpData</div>
|Name|Type|Description|
|---|---|---|
|**count**|Integer| |
|**ips**|[StatisticsTopIpItem[]](querystatisticstopip#statisticstopipitem)| |
### <div id="statisticstopipitem">StatisticsTopIpItem</div>
|Name|Type|Description|
|---|---|---|
|**ip**|String| |
|**rank**|Integer| |
|**value**|Integer| |
|**fullValue**|Object|Search result, the type is HashMap<String, Object>|

## Return Code
|Return Code|Description|
|---|---|
|**200**|OK|