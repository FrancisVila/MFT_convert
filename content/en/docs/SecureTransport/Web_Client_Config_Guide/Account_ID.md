{
    "title": "Control the displayed user information",
    "linkTitle": "Control the displayed user information",
    "weight": "160"
}By default, ST Web Client displays the name of the logged-in user in the **Welcome** menu located in the upper right corner. As an administrator, you can control whether and what user information is displayed there.

## Hide user information

Modify the `stwebclient.config.json` configuration file to add `displayAccountId` property and set `enabled` to `false`.

1.  { 
        "features": {
           "displayAccountId" : {
            "enabled": false  
           },
         }
         ....
        }

Then, refresh the browser to apply the changes.

## Change the displayed user information

You can specify the user information to be displayed under "Welcome" by adding the `preferredAttribute` property in the `stwebclient.config.json` configuration file and setting its value to your most preferred option.

It takes the following values ordered from highest to lowest precedence:

-   `loginName` - displays the login name of the account (corresponds to the **Login Name** field in the account settings)
-   `accountName` - displays the name of the account (corresponds to the **Account Name** field in the account settings)
-   `emailContact` - displays the email of the logged-in user (corresponds to the **Email Contact** field in the account settings)

As **Email Contact** is an optional field, if it is not filled-in, then the next-highest precedence value will be taken. For example, for the following code snippet where the value is set to `emailContact`:

1.   "displayAccountId": {
           "preferredAttribute": "emailContact" 
         } 
         ....
        }                               

The result would be: If an email address is filled-in in the **Email Contact** field in the account settings, it will be displayed in the **Welcome** menu. If the filed is blank, then the login name of the account will be displayed.

After you set the parameter, you need to refresh the browser to apply the changes.
