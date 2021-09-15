{
    "title": "File services interface protocol transfer sites",
    "linkTitle": "File services interface protocol transfer sites",
    "weight": "210"
}Each file services interface protocol can have different required and optional parameters as configured by the developer in the file services interface protocol registry file. The developer who created the transfer site protocol can provide you with a list of required and optional parameters with descriptions and valid values.

The fields under **Site Settings** are required. If they have default values in the file services interface registry file, the Administration Tool displays those values when the transfer protocol is selected.

To specify a password, select **Use Password** and type the password.

The fields in the **Optional Parameters** table are not required.

-   To add an optional parameter, select its name from the **Parameter** list, type a value in the **Value** column, click Add.
-   To edit a parameter value, click the Edit icon (![Edit](TransferSiteParameter_DeleteButton_14x13.png)) type a new value in the **Value** column, and click the Save icon (![Save](TransferSiteParameter_DeleteButton_14x13.png)).
-   To delete a parameter, click the Delete icon (![Delete](TransferSiteParameter_DeleteButton_14x13.png)).

You can create a file services interface protocol transfer site using a site template. If you select a template from the **Site Template** list, the transfer site page displays the values from the site template and the list of placeholders you can specify.

You cannot edit the values in the **Site Template Setting** or the **Optional Parameters**. When you select a site template, the **Site Template Placeholders** fields get the default values from the template. You can type values for these placeholders referenced in the other fields. Select **Use Default** to always use the current default value from the template if it is updated.

You can use a site template to define a file services interface protocol transfer site. For more information, see [Site templates](../../../c_st_advancedaccountadministration/c_st_sitetemplates).

For more information about file services interface protocols for receiving files from other systems, see [File services interface transfers](../../../c_st_fileservicesinterfacetransfers).

**Related topics:**

-   [AS2 transfer sites](../r_st_as2transfersites)
-   [Connect:Direct transfer sites](../r_st_connectdirecttransfersites)
-   [Folder Monitor transfer sites](../r_st_foldermonitortransfersites)
-   [FTP(S) transfer sites](../transfersites-ftp)
-   [Generic HTTP transfer sites](../transfersites-generichttp)
-   [HTTP(S) transfer sites](../transfersites-http)
-   [PeSIT transfer sites](../transfersites-pesit)
-   [SSH transfer sites](../transfersites-ssh)
-   [System to Human transfer sites](../transfersites-s2h)
-   [Manage transfer sites](../t_st_transfersites)
