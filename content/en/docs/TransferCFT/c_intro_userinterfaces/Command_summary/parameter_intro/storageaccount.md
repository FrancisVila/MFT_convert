{
    "title": "storageaccount",
    "linkTitle": "storageaccount",
    "weight": "3430"
}### storageaccount

CFTSEND, CFTRECV

{ string 32 characters }

This parameter points to data stored in UCONF (specifically, the access key identifier aws.credentials.&lt;user>.access\_key\_id, and the access key secret aws.credentials.&lt;user>.secret\_access\_key) for Amazon S3 credentials.

You can use the following commands to display the storageaccount value: LISTCAT content=full/debug, CFTEXT, DISPLAY content=debug, and LISTPARM.
