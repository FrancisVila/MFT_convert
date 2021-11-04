{
    "title": "Access Control",
    "linkTitle": "Access Control",
    "weight": "170"
}Use the `"fileOperations"` section to control the end-users' ability to create, move, rename, or delete files and folders.

All options are of type Boolean with default value `true` (no restrictions).


    {
        ...
        "accessControl": {
            "fileOperations": {
                "createFolder": {
                    "enabled": true
                },
                "moveFile": {
                    "enabled": true
                },
                "renameFileOrFolder": {
                    "enabled": true
                },
                "deleteFileOrFolder": {
                    "enabled": true
                }
            }
        },
        ...
    }

> **Note:**
>
> The above section duplicates server settings and must be maintained together with all related settings in the SecureTransport Administration Tool. The restrictions target only the ST Web Client user interface - the users have other channels to bypass them if the server has more permissive settings.

 
