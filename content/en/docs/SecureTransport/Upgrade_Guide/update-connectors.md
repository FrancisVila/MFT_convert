{
    "title": "Update Amazon S3 and SharePoint transfer sites",
    "linkTitle": "Update Amazon S3 and SharePoint transfer sites",
    "weight": "100"
}Starting with {{< SecureTransport/componentshortname  >}} {{< SecureTransport/releasenumber  >}}, the Amazon S3 and MS SharePoint connectors are released separately from the GA release. Their latest versions that are compatible with {{< SecureTransport/componentshortname  >}} {{< SecureTransport/releasenumber  >}} are available for download from [AMPLIFY Repository](https://repository.axway.com/).

For a full list of connectors that are supported with {{< SecureTransport/componentshortname  >}}, see <a href="https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm" class="MCXref xref">Axway and third-party software support</a>.

If you have an Amazon S3 or a SharePoint transfer site configured on your {{< SecureTransport/securetransportname  >}} 5.4 installation, after upgrading to {{< SecureTransport/releasenumber  >}}, you need to update the corresponding connectors.

To update a connector, follow the procedure, where &lt;FILEDRIVEHOME> is the {{< SecureTransport/componentshortname  >}} installation directory:

1.  Download the connector from AMPLIFY Repository.  
    -   [Amazon S3 Connector for Axway SecureTransport](https://repository.axway.com/product-extensions/views/amazon-s3-connector-for-securetransport)
    -   [MS SharePoint Connector for Axway SecureTransport](https://repository.axway.com/product-extensions/views/sharepoint-connector-for-securetransport)

2.  Execute the following commands to remove the old binaries.  

    -   for Amazon S3

    <!-- -->



        rm -rf <FILEDRIVEHOME>/plugins/transferSites/axway-site-s3

        rm -f FILEDRIVEHOME>/plugins/transferSites/axway-site-s3.jar

3.  for MS SharePoint

4.  Extract the connector's zip file.  

    -   for Amazon S3

    <!-- -->


        unzip securetransport-plugins-site-s3-* -d <FILEDRIVEHOME>/plugins/transferSites/

5.  for MS SharePoint

6.  Restart {{< SecureTransport/componentshortname >}} to load the new configuration.  


        <FILEDRIVEHOME>/bin/stop_all

        <FILEDRIVEHOME>/bin/start_all

 
