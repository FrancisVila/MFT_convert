{
    "title": "Lit/u0435 mode",
    "linkTitle": "Lite mode",
    "weight": "150"
}Lite mode is a lightweight version of the . It offers all basic functionality you would expect from the Web Client in a simplistic view.

Because of this, certain features and views in the Lite mode are disabled. For example, in Lite mode you can have only All files view, while the Mailbox view is disabled. As a result, the Address book feature is disabled and you cannot access your contacts.

Other disabled features include the File sharing action, Transfer queue, navigation tabs, ASCII transfer mode, and some Accessibility shortcuts. Also, in Lite mode only the basic navigation with breadcrumbs is available. These changes also apply to the mobile view.

To enable Lite mode, add the following key to the custom `stwebclient.config.json` configuration file.


    {
     ...
     "liteMode": {
        "enabled": true
     }     

 

> **Note:**
>
> When you enable Lite mode, it overrides the settings of certain features and views, regardless of their configuration in the stwebclient.config.json file.
