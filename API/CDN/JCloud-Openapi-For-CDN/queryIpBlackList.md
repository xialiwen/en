# queryIpBlackList


## Description
Search ip blacklist

## Request Method
GET

## Request Address
https://cdn.jdcloud-api.com/v1/domain/{domain}/ipBlackList

|Name|Type|Required or Not|Default Value|Description|
|---|---|---|---|---|
|**domain**|String|True| |User Domain|

## Request Parameter
None


## Return Parameter
|Name|Type|Description|
|---|---|---|
|**result**|Result| |
|**requestId**|String| |

### Result
|Name|Type|Description|
|---|---|---|
|**domain**|String|Domain|
|**ips**|Object[]|Blacklist List|
|**status**|String|Blacklist List Status, on: enabled, off: disabled|

## Return Code
|Return Code|Description|
|---|---|
|**200**|OK|
|**404**|NOT_FOUND|
