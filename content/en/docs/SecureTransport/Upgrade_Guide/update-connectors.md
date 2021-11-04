{
    "title": "Update Amazon S3 and SharePoint transfer sites",
    "linkTitle": "Update Amazon S3 and SharePoint transfer sites",
    "weight": "100"
}Starting with <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Release_Number variable">5.5</span>, the Amazon S3 and MS SharePoint connectors are released separately from the GA release. Their latest versions that are compatible with <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Release_Number variable">5.5</span> are available for download from [AMPLIFY Repository](https://repository.axway.com/).

For a full list of connectors that are supported with <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, see <a href="https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm" class="MCXref xref">Axway and third-party software support</a>.

If you have an Amazon S3 or a SharePoint transfer site configured on your <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> 5.4 installation, after upgrading to <span class="mc-variable axway_variables.Release_Number variable">5.5</span>, you need to update the corresponding connectors.

To update a connector, follow the procedure, where &lt;FILEDRIVEHOME> is the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation directory:

1.  Download the connector from AMPLIFY Repository.  
    -   [Amazon S3 Connector for Axway SecureTransport](https://repository.axway.com/product-extensions/views/amazon-s3-connector-for-securetransport)
    -   [MS SharePoint Connector for Axway SecureTransport](https://repository.axway.com/product-extensions/views/sharepoint-connector-for-securetransport)
2.  Execute the following commands to remove the old binaries.  
    -   for Amazon S3
    -   for MS SharePoint
3.  Extract the connector's zip file.  
    -   for Amazon S3
    -   for MS SharePoint
4.  Restart <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to load the new configuration.  


        <FILEDRIVEHOME>/bin/stop_all

        <FILEDRIVEHOME>/bin/start_all

 
