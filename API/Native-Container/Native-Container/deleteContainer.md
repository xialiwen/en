# deleteContainer


## Description
The container must have the status of stopped, running or error. <br>
The instance paid by volume will keep running until it is deleted. The instance not used anymore can be passively stopped through this interface. <br>
Only the instance with the billing type by volume can be passively deleted. The container with monthly package expired can also be deleted. Please report to the ticket system for other situations. The container with billing status exception can’t be deleted.


## Request method
DELETE

## Request address
https://nativecontainer.jdcloud-api.com/v1/regions/{regionId}/containers/{containerId}

|Name|Type|Required or not|Default value|Description|
|---|---|---|---|---|
|**regionId**|String|True| |Region ID|
|**containerId**|String|True| |Container ID|

## Request parameter
None


## Response parameter
|Name|Type|Description|
|---|---|---|
|**requestId**|String| |


## Response code
|Return code|Description|
|---|---|
|**200**|OK|
|**400**|Invalid parameter|
|**401**|Authentication failed|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|
