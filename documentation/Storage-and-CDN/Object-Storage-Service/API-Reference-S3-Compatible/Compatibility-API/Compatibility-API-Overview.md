# Compatible APIs List

The JD Cloud OSS compatible AWS S3 APIs and the description are as follows:
# About Service Operation
| API supported by OSS|API introduction|API Reference of JD Cloud S3 API|API Reference of AWS S3 |
|-|-|-|-|
|GET Service(List Bucket）|Obtain all Buckets under a User|Compatible [GET Service](./Service-Related/Get-Service-2.md)| [GET Service](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTServiceGET.html)|

# About Bucket Operation

|api supported by Object Storage Service|api introduction|JD Cloud S3 API Reference| AWS S3 API Reference |
|-|-|-|-|
|PUT Bucket|Create a Bucket, default permission is Private|Compatible [PUT Bucket](./Operations-On-Bucket/Put-Bucket-2.md)| [PUT Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUT.html)|
|HEAD Bucket|Confirm whether a Bucket exists or not and has right to access.<br>If a Bucket exists and has right to access, return 200 OK If the assigned bucket does not exist, return 404 Not Found|Compatible [HEAD Bucket](./Operations-On-Bucket/Head-Bucket-2.md)| [HEAD Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketHEAD.html)|
|GET Bucket（List Object）|Acquire the partial or all Object information under a certain Bucket (Compatible Version2)|Compatible[GET Bucket](./Operations-On-Bucket/Get-Bucket-2.md)| [GET Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/v2-RESTBucketGET.html)|
|DELETE Bucket|Delete the assigned Bucket|Compatible [DELETE Bucket](./Operations-On-Bucket/Delete-Bucket-2-Compatibility-API.md)| [DELETE Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETE.html)|
|List MultiPart Uploads|Obtain the MultiPart task uploaded under a Bucket|Compatible [List MultiPart Uploads](./Operations-On-Bucket/List-Multipart-Uploads-2.md)| [List MultiPart Uploads](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadListMPUpload.html)|
|GET Bucket policy|Obtain policy on the assigned Bucket|Compatible [GET Bucket policy](./Operations-On-Bucket/Get-Bucket-Policy-2.md)| [GET Bucket policy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETpolicy.html)|
|PUT Bucket policy|Add or edit policy on the assigned Buckety|Compatible [PUT Bucket policy](./Operations-On-Bucket/Put-Bucket-Policy-2.md)| [PUT Bucket policy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTpolicy.html)|
|DELETE Bucket policy|Delete policy on the assigned Bucket|Compatible [DELETE Bucket policy](./Operations-On-Bucket/Delete-Bucket-Policy-2.md)| [DELETE Bucket policy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEpolicy.html)|
|PUT Bucket acl|Set acl on the assigned Bucket|Compatible [PUT Bucket acl](./Operations-On-Bucket/Put-Bukcet-acl-2.md)| [PUT Bucket acl](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTacl.html)|
|GET Bucket acl|Obtain acl on the assigned Bucket|Compatible [GET Bucket acl](./Operations-On-Bucket/GET-Bucket-Acl-2.md)| [GET Bucket acl](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETacl.html)|
|PUT Bucket cors|Add CORS rules for the assigned Bucket|Compatible [PUT Bucket cors](./Operations-On-Bucket/Put-Bucket-Cors-2.md)| [PUT Bucket cors](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTcors.html)|
|GET Bucket cors|Obtain CORS rules for the assigned Bucket|Compatible [GET Bucket cors](./Operations-On-Bucket/Get-Bucket-Cors-2.md)| [GET Bucket cors](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETcors.html)|
|DELETE Bucket cors|Delete CORS rules for the assigned Bucket|Compatible [DELETE Bucket cors](./Operations-On-Bucket/Delete-Bucket-Cors-2.md)| [DELETE Bucket cors](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|PUT Bucket website|Add static website hosting rules for the assigned Bucket (note: The interface is compatible, but the details of rules are different from S3)|Compatible [PUT Bucket website](./Operations-On-Bucket/Put-Bucket-Website-2.md)| [PUT Bucket website](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|GET Bucket website|Obtain static website hosting rules for the assigned Bucket (note: The interface is compatible, but the details of rules are different from S3)|Compatible [GET Bucket website](./Operations-On-Bucket/Get-Bucket-Website-2.md)|[GET Bucket website](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|DELETE Bucket website|Delete static website hosting rules for the assigned Bucket (note: The interface is compatible, but the details of rules are different from S3)|Compatible [DELETE Bucket website](./Operations-On-Bucket/Delete-Bucket-Website-2.md)|[DELETE Bucket website](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|PUT Bucket Replication|Create and modify cross-region replication configuration|Not support:Account，Role，Owner AccessControlTranslation SourceSelectionCriteria<br>Compatible [PUT Bucket Replication](./Operations-On-Bucket/Put-Bucket-Replication-2.md)|[PUT Bucket Replication](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTreplication.html)|
|GET Bucket Replication|Return cross-region replication configuration set on Bucket|Compatible [GET Bucket replication](./Operations-On-Bucket/Get-Bucket-Replication-2.md)|[GET Bucket replication](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETreplication.html)|
|DELETE Bucket Replication|Delete the enabled cross-region replication configuration, the target Bucket and object remain exist after deletion|Compatible [Delete Bucket replication](./Operations-On-Bucket/Delete-Bucket-Replication-2.md)|[Delete Bucket replication](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEreplication.html)|
|PUT Bucket notification|Assign a Bucket to add NotificationConfiguration|Not support:CloudFunction，Queue<br>Only support: Topic (for details, see [callback notification](../../Operation-Guide/Manage-Bucket/Callback-Notification-2.md))<br>Compatible [PUT Bucket notification](./Operations-On-Bucket/PUT-Bucket-Notification-2.md)|[PUT Bucket notification](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTnotification.html)|
|GET Bucket notification|Return NotificationConfiguration set on Bucket|Compatible [GET Bucket notification](./Operations-On-Bucket/GET-Bucket-Notification-2.md)|[GET Bucket notification](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETnotification.html)|
|GET Bucket encryption|Return the user’s default encryption configuration of OSS bucket|Compatible[GET Bucket encryption](./Operations-On-Bucket/Get-Bucket-Encryption-2.md)|[GET Bucket encryption](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETencryption.html)|
|PUT Bucket encryption|It is used for setting bucket default encryption mode|Compatible[PUT Bucket encryption](./Operations-On-Bucket/Put-Bucket-Encryption-2.md)|[PUT Bucket encryption](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTencryption.html)|
|DELETE Bucket encryption|Delete the default encryption configuration of OSS bucket|Compatible[DELETE Bucket encryption](./Operations-On-Bucket/Delete-Bucket-Encryption-2.md)|[DELETE Bucket encryption](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEencryption.html)|
|PUT Bucket lifecycle|Set Life Cycle Rules of Bucket|Do not support:Transition, AbortIncompleteMultipartUpload<br>Compatible to: [PUT Bucket lifecycle](./Operations-On-Bucket/Put-Bucket-Lifecycle.md)|[PUT Bucket lifecycle](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTlifecycle.html)|
|GET Bucket lifecycle|Set Life Cycle Rules of Bucket|Compatible to: [GET Bucket lifecycle](./Operations-On-Bucket/Get-Bucket-Lifecycle.md)|[GET Bucket lifecycle](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETlifecycle.html)|
|DELETE Bucket lifecycle|Delete Life Cycle Rules of Bucket|Compatible to: [DELETE Bucket lifecycle](./Operations-On-Bucket/Delete-Bucket-Lifecycle.md)|[DELETE Bucket lifecycle](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETElifecycle.html)|
Put Bucket tagging|Set Bucket tagging|Compatible: [Put Bucket tagging](./Operations-On-Bucket/Put-Bucket-Tagging.md)|[Put Bucket tagging](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTtagging.html)|
Get Bucket tagging|Get Bucket tagging|Compatible: [Get Bucket tagging](./Operations-On-Bucket/Get-Bucket-Tagging.md)|[Get Bucket tagging](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETtagging.html)

# About Object Operation 

|api supported by Object Storage Service|api introduction|JD Cloud S3 API Reference| AWS S3 API Reference |
|-|-|-|-|
|PUT Object|Upload an Object to OSS|Compatible [PUT Object](./Operations-On-Objects/Put-Object-2.md)| [PUT Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectPUT.html)
|GET Object|Obtain the Meta and data of an Object to obtain all data or use Range to assign to obtain part of the data|Compatible [GET Object](./Operations-On-Objects/Get-Object-2.md)| [GET Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectGET.html)|
|HEAD Object|Obtain the Meta of an Object|Compatible [HEAD Object](./Operations-On-Objects/Head-Object-2.md)| [HEAD Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectHEAD.html)|
|DELETE Object|Delete an Object|Compatible [DELETE Object](./Operations-On-Objects/Delete-Object-2.md)| [DELETE Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectDELETE.html)|
|Delete Multiple Objects|Users can delete multiple Objects in the same Bucket by one HTTP request|Not support:version<br>Compatible [Delete Multiple Objects](./Operations-On-Objects/Delete-Multiple-Objects-2.md)|[Delete Multiple Objects](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/multiobjectdeleteapi.html)|
|Initiate MultiPart Upload|Initialize a MultiPart upload task|Compatible [Initiate Mutipart Upload](./Operations-On-Objects/Initiate-Multipart-Upload-2.md)| [Initiate MultiPart Upload](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadInitiate.html)|
|Upload Part|Upload a Part to OSS|Compatible [Upload Part](./Operations-On-Objects/Upload-Part-2.md)| [Upload Part](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadUploadPart.html)|
|Complete MultiPart Upload|Combine multiple parts uploaded into an Object|Compatible [Complete Multipart Upload](./Operations-On-Objects/Complete-Multipart-Upload-2.md)| [Complete MultiPart Upload](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadComplete.html)|
|Abort MultiPart Upload|Abort a MultiPart upload task|Compatible [Abort MultiPart Upload](./Operations-On-Objects/Abort-Multipart-Upload-2.md)| [Abort MultiPart Upload](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadAbort.html)|
|List Parts|Obtain information of the part already uploaded by the assigned uploadid|Compatible [List Parts](./Operations-On-Objects/List-Parts-2.md)| [List Parts](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadListParts.html)|
|POST Object|Upload an Object by POST Object|Compatible [POST Object](./Operations-On-Objects/Post-Object-2.md)|[POST Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectPOST.html)|
|Put Object Copy|Copy an object already existing on OSS into another object|Not support:x-amz-copy-source-if-match，<br>x-amz-copy-source-if-none-match，<br>x-amz-copy-source-if-unmodified-since，<br>x-amz-copy-source-if-modified-since，<br>x-amz-tagging-directive<br>x-amz-storage-class<br>Support:STANDARD/REDUCED_REDUNDANCY<br>Compatible [PUT Object - Copy](./Operations-On-Objects/Put-Object-Copy-2.md)|[PUT Object - Copy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectCOPY.html)|
|Upload Part Copy|By copying data from an existed Object to upload a Part|Not support:x-amz-copy-source-if-match，<br>x-amz-copy-source-if-none-match，<br>x-amz-copy-source-if-unmodified-since，<br>x-amz-copy-source-if-modified-since<br>Compatible [Upload Part - Copy](./Operations-On-Objects/Upload-Part-Copy-2.md)|[Upload Part - Copy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadUploadPartCopy.html)|
|POST Object restore|Restore archival storage objects to get temporary replicas|Unsupported: Select <br>Compatible[POST Object restore](./Operations-On-Objects/Post-Object-Restore.md)|[POST Object restore](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectPOSTrestore.html)|