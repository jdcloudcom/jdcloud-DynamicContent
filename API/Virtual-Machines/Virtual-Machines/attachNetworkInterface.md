# attachNetworkInterface


## Description
Attach an ENI to a VM.
The status of the VM must be <b>running</b> or <b>stopped</b>, and the attachment is only available when there is no task in progress.
If some EIPs have associated with the ENI that to be attached, the az of the EIPs needs to be consistent with the az of the VM, or be all-AZs.
The number of the ENIs attached to the VM cannot exceed the limit of its instance type. Can query <a href="http://docs.jdcloud.com/virtual-machines/api/describeinstancetypes">DescribeInstanceTypes</a>API to get the upper limit of a specified instance type.
The ENI and the VM must be in the same vpc.


## Request method
POST

## Request address
https://vm.jdcloud-api.com/v1/regions/{regionId}/instances/{instanceId}:attachNetworkInterface

|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**regionId**|String|True| |Region ID|
|**instanceId**|String|True| |VM ID|

## Request parameter
|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**networkInterfaceId**|String|True| |ENI ID|
|**autoDelete**|Boolean|False| |Auto-delete with the machine, False by default.|


## Response parameter
None


## Response code
|Return code|Description|
|---|---|
|**200**|OK|
|**400**|Invalid parameter|
|**401**|Authentication failed|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|
