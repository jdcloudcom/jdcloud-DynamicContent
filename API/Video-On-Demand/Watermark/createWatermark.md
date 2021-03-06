# createWatermark


## Description
Add watermarks

## Request Method
POST

## Request Address
https://vod.jdcloud-api.com/v1/watermarks


## Request Parameter
|Name|Type|Required or Not|Default Value|Description|
|---|---|---|---|---|
|**name**|String|True| |Watermark Name. Support Chinese or English letters and numbers only. Length cannot exceed 128 characters. UTF-8 code. <br>|
|**imgUrl**|String|True| |Image Address|
|**width**|String|True| |Watermark width. <br>When sizeUnit = pixel, the value is the integer from the value range [8, 4096]<br>When sizeUnit = percent, the value is the decimal from the value range [0, 100]<br>|
|**height**|String|True| |Watermark height. <br>When sizeUnit = pixel, the value is the integer from the value range [8, 4096]<br>When sizeUnit = percent, the value is the decimal from the value range [0, 100]<br>|
|**sizeUnit**|String|False| |Size Unit. Value range: <br>  pixel - pixel<br>  percent - percent<br>the default value is pixel<br>|
|**position**|String|True| |Watermark Location. Value range: <br>  LT - left top<br>  RT - right top<br>  LB - left bottom<br>  RB - right bottom<br>|
|**offsetX**|String|True| |Horizontal shift. <br>When offsetUnit = pixel, the value is the integer from the value range [8, 4088]<br>When offsetUnit = percent, the value range is the decimal from the value range [0, 100]<br>|
|**offsetY**|String|True| |Vertical shift. <br>When offsetUnit = pixel, the value is the integer from the value range [8, 4088]<br>When offsetUnit = percent, the value range is the decimal from the value range [0, 100]<br>|
|**offsetUnit**|String|False| |Shifting Unit. Value range: <br>  pixel - pixel<br>  percent - percent<br>the default value is pixel<br>|


## Return Parameter
|Name|Type|Description|
|---|---|---|
|**result**|[Result](createwatermark#result)|Add watermark result|
|**requestId**|String|Request ID|

### <div id="result">Result</div>
|Name|Type|Description|
|---|---|---|
|**id**|Long|Watermark ID|
|**name**|String|Watermark Name. Support Chinese or English letters and numbers only. Length cannot exceed 128 characters. UTF-8 code. <br>|
|**imgUrl**|String|Image Address|
|**width**|String|Watermark width. <br>When sizeUnit = pixel, the value is the integer from the value range [8, 4096]<br>When sizeUnit = percent, the value is the decimal from the value range [0, 100]<br>|
|**height**|String|Watermark height. <br>When sizeUnit = pixel, the value is the integer from the value range [8, 4096]<br>When sizeUnit = percent, the value is the decimal from the value range [0, 100]<br>|
|**sizeUnit**|String|Size Unit. Value range: <br>  pixel - pixel<br>  percent - percent<br>the default value is pixel<br>|
|**position**|String|Watermark Location. Value range: <br>  LT - left top<br>  RT - right top<br>  LB - left bottom<br>  RB - right bottom|
|**offsetX**|String|Horizontal shift. <br>When offsetUnit = pixel, the value is the integer from the value range [8, 4088]<br>When offsetUnit = percent, the value range is the decimal from the value range [0, 100]<br>|
|**offsetY**|String|Vertical shift. <br>When offsetUnit = pixel, the value is the integer from the value range [8, 4088]<br>When offsetUnit = percent, the value range is the decimal from the value range [0, 100]<br>|
|**offsetUnit**|String|Shifting Unit. Value range: <br>  pixel - pixel<br>  percent - percent<br>the default value is pixel<br>|
|**createTime**|String|Creation Time|
|**updateTime**|String|Modification Time|

## Return Code
|Return Code|Description|
|---|---|
|**200**|OK|
|**400**|Invalid parameter|
|**401**|Authentication failed|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|

## Request Example
POST
```
https://vod.jdcloud-api.com/v1/watermarks

```
```
{
    "height": 50, 
    "imgUrl": "/image/ecd9066c0f2c8e4bbd8a9fd7ae37965f.PNG", 
    "name": "Mango", 
    "offsetX": 32, 
    "offsetY": 16, 
    "position": "LT", 
    "unit": "pixel", 
    "width": 100
}
```

## Return Example
```
{
    "requestId": "edfc74ea-be4c-418b-b841-31ddd2b33203", 
    "result": {
        "createTime": "2019-04-16T15:51:32Z", 
        "height": 50, 
        "id": 1, 
        "imgUrl": "http://s3.cn-north-1-stag.jcloudcs.com/vod-storage-72757/image/ecd9066c0f2c8e4bbd8a9fd7ae37965f.PNG", 
        "name": "Mango", 
        "offsetX": 32, 
        "offsetY": 16, 
        "position": "LT", 
        "unit": "pixel", 
        "updateTime": "2019-04-16T15:51:32Z", 
        "width": 100
    }
}
```
