# Report Monitoring Data
The function of Custom Metric Monitoring provides you with an interface for reporting monitoring data, so that you can report the time series data collected by yourself to the Monitoring. OpenAPI and command line tool CLI are currently supported for reporting.  
## OpenAPI Reporting

### Reporting Interface Description

1. Interface Name: putMetricData

2. Public Domain Name  

Region | Domain name
---|---
cn-north-1 |monitor.cn-north-1.jdcloud-api.com
cn-south-1 |monitor.cn-south-1.jdcloud-api.com
cn-east-1 |monitor.cn-east-1.jdcloud-api.com
cn-east-2 |monitor.cn-east-2.jdcloud-api.com

3. Intranet Domain  

Region | Domain
---|---
cn-north-1|monitor.internal.cn-north-1.jdcloud-api.com
cn-south-1 |monitor.internal.cn-south-1.jdcloud-api.com
cn-east-1 |monitor.internal.cn-east-1.jdcloud-api.com
cn-east-2 |monitor.internal.cn-east-2.jdcloud-api.com

4. Support batch reporting mode. A single request can contain up to 50 data points; the data size shall not exceed 256k.

Note: For Getting Started Guide on OpenAPI, please see the <a href="https://github.com/jdcloudcom/en/blob/translationUse/API/Common-Declaration/Introduction.md">public description</a>

### Request Method

POST   https://{Domain name}/v1/customMetrics

For example: POST    https://monitor.cn-north-1.jdcloud-api.com/v1/customMetrics

### Request Parameter

Name | Type | Required or Not | Description
---|---|---|---
metricDataList|	MetricDataCm[] |	False |	Data Parameter   

#### MetricDataCm

Name | Type | Required or Not | Description
---|---|---|---
dimensions|Object |True|Data dimension, data type is map type, support at least one, up to five tags, no more than 255 bytes in total length, only English, numbers, underlines_, dot., [0-9][a-z] [A-Z] [. _ ] are allowed, others will return err
metric|	String |True |Metric name, no more than 255 bytes in length, only English, numbers, underlines_, dot., [0-9][a-z] [A-Z] [. _ ] are allowed, others will return err               
namespace|	String |True |Naming space,  no more than 255 bytes in length, only English, numbers, underlines_, dot., [0-9][a-z] [A-Z] [. _ ] are allowed, others will return er               
timestamp|Integer|True|Timestamp for reporting data points only supports 10-bit, second timestamp, the time of the past 30 days cannot be written in                              
type |Integer|True |Data type, only the value 1, original data, can be entered now.                          
values |	Object | True |In the indicator value set, the data type must be the map type, key is the data type, value is the data value, type=1 is supported now and key only can be "value".  

### Return Parameter  

Name | Type | Required or not 
---|---|---
error |Object| Error information.     
requestId|String |Request ID                        
result |Result |                
                      
#### Result
Name | Type | Required or not 
---|---|---
errMetricDataList|MetricDataList[]|
success|Boolean  |All successful write-ins are true, otherwise are false   

#### MetricDataList
Name | Type | Required or not 
---|---|---
errDetail|string	| Error data Description
errMetricData |string |Error data              

### Return Code  
Name | Type 
---|---
200	|OK
400	|invalid parameter
500 |internal server error
429	|quota exceed


### Sample Code

Note: When using this example directly, please replace the timestamp parameter with the latest 10-bit second-level time stamp, otherwise it will fail to write (the written time stamp is not allowed to exceed the data of the past 30 days).  

Request Sample
```
{
	"metricDataList": [
	  {
			"namespace": "test",
			"metric": "vm.mem.usage1",
			"dimensions": {
				"host": "1.2.3.23",
				"datacenter": "cn-north-1"
			},
			"timestamp": 1552446075,
			"type": 1,
			"values": {
				"value": "12342213"
			}
		},

		{
			"namespace": "test1",
			"metric": "vm.cpu.usage",
			"dimensions": {
				"host": "1.2.3.19",
				"tag": "bj"
			},
			"timestamp": 1552446075,
			"type": 2,
			"values": {
				"value": "12342213"
			}
		}
	]
}
```

Return Sample

```
success：

{
    "requestId": "1111",
    "result": {
        "success": true,
        "errMetricDataList": []
    }
}

fail：
{
	"requestId": "1111",
	"result": {
		"success": false,
		"errMetricDataList": [{
			"ErrMetricData": "{\"namespace\":\"test1\",\"metric\":\"vm.cpu.usage\",\"dimensions\":{\"host\":\"1.2.3.19\",\"region\":\"bj\",\"tag\":\"bj\",\"tag2\":\"bj\",\"tag3\":\"bj\",\"tag4\":\"bj\"},\"timestamp\":1540361379,\"type\":2,\"values\":{\"avg\":\"80\",\"max\":\"32424244120\"}}",
			"errDetail": "Invalid dimensions,dimensions num limited in 1 to 5 and not null"
		}]
	},
	"error": {
		"code": 400,
		"message": "INVALID_ARGUMENT",
		"status": "INVALID_ARGUMENT",
		"details": null
	}
}

```

## CLI Reporting 
### Installation of CLI  
About how to install, please refer to <a href="https://docs.jdcloud.com/en/cli/installation"> for installation instructions </a> .
### Configuration Environment  

Configure the KEY, location area (region-id) and gateway address (endpoint) and edit /root/.jdc/config
```
vi ~/.jdc/config
```

```
[default]
access_key = YourAccessKeyID
secret_key = YourAccessKeySecret
region_id = cn-north-1
endpoint = monitor.cn-north-1.jdcloud-api.com
scheme = https
timeout = 20
```  
The region_id of different regions and reported gateway endpoint addresses are as follows:  

Region |region_id |Public Network endpoint|Intranet endpoint
---|---|---|---
cn-north-1 |cn-north-1| monitor.cn-north-1.jdcloud-api.com |monitor.internal.cn-north-1.jdcloud-api.com
cn-south-1 |cn-south-1| monitor.cn-south-1.jdcloud-api.com |monitor.internal.cn-south-1.jdcloud-api.com
cn-east-1  |cn-east-1 |monitor.cn-east-1.jdcloud-api.com   |monitor.internal.cn-east-1.jdcloud-api.com
cn-east-2  |cn-east-2 | monitor.cn-east-2.jdcloud-api.com  |monitor.internal.cn-east-2.jdcloud-api.com

### Report Monitoring Data  
Use the put-metric-data interface to Report Monitoring Data, examples are as follows:  
```
jdc monitor put-metric-data --input-json '{"metricDataList": [{"namespace": "test_ns","metric": "vm.cpu.usage1","dimensions": {"host": "10.10.10.23","datacenter": "cn_north_1"},"timestamp": 1544425695,"type": 1,"values": {"value": "12342213"}}]}'
```  
Note: Only monitoring data in the latest one week can be reported. Please modify the time stamp in the timestamp in the above example to the UNIX time you currently report.

The example for successful return is as follows:
```
{
    "error": null, 
    "result": {
        "errMetricDataList": [], 
        "success": true
    }, 
    "request_id": "bg9ofp78ikqqgvastas64owpqmoijk77"
}
```
