{
    "title": "Modify the view configuration",
    "linkTitle": "Modify the view configuration",
    "weight": "110"
}The <span class="mc-variable SecureTransport_Variables.st_web_client variable">ST Web Client</span> has two views:

-   File view
-   Mailbox view

The default view can be changed and a view can be disabled.

To modify the view configuration, copy the `views` key from the `C/config/default.config.json` file into the `custom/stwebclient.config.json` file, and edit the custom configuration file as described in <a href="../config_files" class="MCXref xref">Configuration files</a>.

The view configuration is located in the `views` key.

## Change the default view

To set the default view, change the `defaultView` parameter. The parameter values are:

-   `allFiles` - File view
-   `mailbox` - Mailbox view

## Enable or disable a view

To enable a view, set the enable parameter for the view to `true`. To disable a view, set the enable parameter for the view to `false`.

 