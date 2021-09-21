{
    "title": "Update Amazon S3 and SharePoint transfer sites",
    "linkTitle": "Update Amazon S3 and SharePoint transfer sites",
    "weight": "100"
}Starting with SecureTransport 5.5, the Amazon S3 and MS SharePoint connectors are released separately from the GA release. Their latest versions that are compatible with SecureTransport 5.5 are available for download from [AMPLIFY Repository](https://repository.axway.com/).

For a full list of connectors that are supported with SecureTransport, see [Axway and third-party software support](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm).

If you have an Amazon S3 or a SharePoint transfer site configured on your SecureTransport 5.4 installation, after upgrading to 5.5, you need to update the corresponding connectors.

To update a connector, follow the procedure, where &lt;FILEDRIVEHOME> is the SecureTransport installation directory:

1.  Download the connector from AMPLIFY Repository.  
    
    -   [Amazon S3 Connector for Axway SecureTransport](https://repository.axway.com/product-extensions/views/amazon-s3-connector-for-securetransport)
    -   [MS SharePoint Connector for Axway SecureTransport](https://repository.axway.com/product-extensions/views/sharepoint-connector-for-securetransport)
2.  Execute the following commands to remove the old binaries.  
    
    -   for Amazon S3
    -   for MS SharePoint
3.  Extract the connector's zip file.  
    
    -   for Amazon S3
    -   for MS SharePoint
4.  Restart SecureTransport to load the new configuration.  
    
    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>rm -rf &lt;FILEDRIVEHOME&gt;/plugins/transferSites/axway-site-s3</code>
</p>
            <p><code>rm -f FILEDRIVEHOME&gt;/plugins/transferSites/axway-site-s3.jar</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

 
