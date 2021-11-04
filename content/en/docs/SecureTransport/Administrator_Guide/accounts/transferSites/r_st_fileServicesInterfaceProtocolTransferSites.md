{
    "title": "File services interface transfer sites",
    "linkTitle": "File services interface protocol transfer sites",
    "weight": "200"
}Each file services interface protocol can have different required and optional parameters as configured by the developer in the file services interface protocol registry file. The developer who created the transfer site protocol can provide you with a list of required and optional parameters with descriptions and valid values.

The fields under **Site Settings** are required. If they have default values in the file services interface registry file, the Administration Tool displays those values when the transfer protocol is selected.

To specify a password, select **Use Password** and type the password.

The fields in the **Optional Parameters** table are not required.

-   To add an optional parameter, select its name from the **Parameter** list, type a value in the **Value** column, click Add.
-   To edit a parameter value, click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) type a new value in the **Value** column, and click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)).
-   To delete a parameter, click the Delete icon (![Delete](/Images/SecureTransport/TransferSiteParameter_DeleteButton_14x13.png)).

You can create a file services interface protocol transfer site using a site template. If you select a template from the **Site Template** list, the transfer site page displays the values from the site template and the list of placeholders you can specify.

You cannot edit the values in the **Site Template Setting** or the **Optional Parameters**. When you select a site template, the **Site Template Placeholders** fields get the default values from the template. You can type values for these placeholders referenced in the other fields. Select **Use Default** to always use the current default value from the template if it is updated.

You can use a site template to define a file services interface protocol transfer site. For more information, see <a href="../../../c_st_advancedaccountadministration/c_st_sitetemplates#Advanced_Accounts_2036285406_1131467" class="MCXref xref">Site templates</a>.

For more information about file services interface protocols for receiving files from other systems, see <a href="../../../c_st_fileservicesinterfacetransfers#FileServicesInterfaceTransfers_2548184958_1041296" class="MCXref xref">File services interface transfers</a>.

**Related topics:**

-   <a href="../r_st_as2transfersites" class="MCXref xref">AS2 transfer sites</a>
-   <a href="../r_st_connectdirecttransfersites" class="MCXref xref">Connect:Direct transfer sites</a>
-   <a href="../r_st_foldermonitortransfersites" class="MCXref xref">Folder Monitor transfer sites</a>
-   <a href="../transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a>
-   <a href="../transfersites-generichttp" class="MCXref xref">Generic HTTP transfer sites</a>
-   <a href="../transfersites-http" class="MCXref xref">HTTP(S) transfer sites</a>
-   <a href="../transfersites-pesit" class="MCXref xref">PeSIT transfer sites</a>
-   <a href="../transfersites-ssh" class="MCXref xref">SSH transfer sites</a>
-   <a href="../transfersites-s2h" class="MCXref xref">System to Human transfer sites</a>
-   <a href="../t_st_transfersites" class="MCXref xref">Manage transfer sites</a>