{
    "title": "Session Management",
    "linkTitle": "Session management",
    "weight": "210"
}Use the `"downloadServerPolling"` section to prevent UI session timeouts when large files are being downloaded.

To enable the download polling:


    {
       ...
       "sessionManagement": {
          downloadServerPolling": {
           "enabled": true
          }
       }
       ...
    }                       

> **Note:**
>
> Download polling depends on transfers API. The Allow this account to submit transfers using the Transfers RESTful API option must be enabled for the user.
