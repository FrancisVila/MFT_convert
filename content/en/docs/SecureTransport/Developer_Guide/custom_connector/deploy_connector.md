{
    "title": "Deploy a custom protocol connector",
    "linkTitle": "Deploy a custom protocol connector",
    "weight": "110"
}In order to configure and deploy a Custom Connector implementation into SecureTransport Server, follow these steps:

1.  After implementing Custom Connector and the User Interface for this connector you should add them to a single jar file. For Site SPI version 1.0, you must create a `MANIFEST.MF` file in the jar file that describes the integration points between SecureTransport and the Custom Connector.  
    The `META-INF/MANIFEST.MF` file must be created with the following properties:  
    

    <table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Property</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Custom-Protocol         </td>
         <td>
            <p>The name of the protocol as displayed in SecureTransport File Tracking. File Tracking also logs the protocol. Should be unique. Maximum of 255 characters.</p>
         </td>
      </tr>
      <tr>
         <td>Protocol-Label         </td>
         <td>The human readable name that is displayed in the drop-box menu of the Pluggable Transfer Site. Maximum of 255 characters.         </td>
      </tr>
      <tr>
         <td>Custom-UI         </td>
         <td>The HTML file, which is injected, when the Pluggable Transfer Site is selected from the drop down menu on the Transfer Sites page.         </td>
      </tr>
      <tr>
         <td>Custom-Site         </td>
         <td>The full name of the class that extends the <code>com.axway.st.plugins.site.CustomSite</code> abstract class and implements the <code>com.axway.st.plugins.site.Connection</code> interface. This is the integration point between <span>SecureTransport</span> and the Custom Transfer Site.          </td>
      </tr>
      <tr>
         <td>Class-Path         </td>
         <td>This property is optional. The Class-Path property is useful for specifying the list of the external libraries your custom connector needs to successfully run. The value of this property must be a space or tab separated list of the external libraries.         </td>
      </tr>
      <tr>
         <td>SPI-Version         </td>
         <td>This property is optional. Specify the used SPI version by the plug-in. Default value is 1.0.         </td>
      </tr>
   </tbody>
</table>

      
    This metadata file is used by SecureTransport to register and use the Custom Connector implementation like a regular Transfer Site.  
    If your Custom Connector implementation depends on third party libraries, you have two implementation approaches:

    -   You can use a fat jar file that stores your classes and the classes from all dependent jars into a one single jar file.
    -   or

    <!-- -->

    -   Add a Class-Path attribute to the `MANIFEST.MF` file, in which you should enumerate your dependent jars separated by spaces or tabs. SecureTransport will add the enumerated libraries to the Custom Connector implementation classpath.

    -   For Site SPI v1.1 or higher use instead the `Plugin-Info.yaml` file.  
        The META-INF/Plugin-Info.yaml must be created with the same properties as described above.  
        Example:

    -   <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>Custom-Protocol: myProtocol</p>            <p>SPI-Version: '1.0':</p>            <p>Custom-Site: com.axway.st.plugins.site.MyProtocol_1_0</p>            <p>Protocol-Label: My Sample Transfer Site (1.0)</p>            <p>Custom-UI: html/mySite-1-0.html</p>            <p>Class-Path: MySite/lib/lib1.jar MySite/lib/lib2.jar MySite/lib_1_0/lib3_1_0.jar</p>            <p>'1.1':</p>            <p>Custom-Site: com.axway.st.plugins.site.MyProtocol_1_1</p>            <p>Protocol-Label: My Sample Transfer Site (1.1)</p>            <p>Custom-UI: html/mySite-1-1.html</p>            <p>Class-Path: MySite/lib/lib1.jar MySite/lib/lib2.jar MySite/lib_1_1/lib3_1_1.jar</p>         </td>      </tr>   </tbody></table>

2.  Deploy Custom Connector into SecureTransport.

When you have produced/created a jar file containing the Custom Connector implementation and a `MANIFEST.MF` file, you should place it into your SecureTransport Server. In the installation folder of SecureTransport 5.3.6 version and above, you will find the following directory:

-   `${FILEDRIVE_HOME}/plugins/transferSites`, where `${FILEDRIVE_HOME}` represents SecureTransport installation directory.

<table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>SecureTransport</span> will look for the latest Site SPI version if more than one is specify.         </td>      </tr></table>

The Custom Connector jar file should be placed in the `${FILEDRIVE_HOME}/plugins/transferSites` directory. This directory is scanned by SecureTransport for jar files with the specific `MANIFEST.MF` file describing the integration points between the custom connector and the SecureTransport Server. For each custom connector, there should be a jar file containing the SecureTransport Pluggable Transfer Site SPI implementation and the `MANIFEST.MF` file. Also, if there are any third party resources that are required by your custom connector implementation and are not included in the Custom Connector jar, they should be placed in a separate directory inside the `${FILEDRIVE_HOME}/plugins/transferSites` directory and be listed in the `MANIFEST.MF` file under Class-Path attribute.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In a cluster environment, you must add the Custom Connector jar file to all nodes of the cluster.         </td>
      </tr>
</table>

Let's assume you have already implemented the simple FTP Custom Connector with a third party dependencies to external library named `sftp.jar`. Then the `MANIFEST.MF` file should look like this:

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">External libraries should be placed in separate directory inside the <code>${FILEDRIVE_HOME}/plugins/transferSites</code> directory.         </td>
      </tr>
</table>

Аdd your Custom Connector implementation jar to the `${FILEDRIVE_HOME}/plugins/transferSites/` directory and the `sftp.jar` file to the `${FILEDRIVE_HOME}/plugins/transferSites/lib/myftp/lib/` directory inside the SecureTransport installation directory. The final directory structure should look like this:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">Custom-Protocol: myftp
Protocol-Label: FTP(S) Sample Transfer Site
Custom-UI: ftpSampleSite.html
Custom-Site: com.axway.st.plugins.site.sdk.ftp.FTPSite
Class-Path: myftp/lib/sftp.jar</pre>
         </td>
      </tr>
   </tbody>
</table>

After your custom connector jar file, including the third party libraries, is placed in the `${FILEDRIVE_HOME}/plugins/transferSites` directory, the SecureTransport Administration Service should be restarted in order to load and register your Custom Connector implementation as a SecureTransport Transfer Site.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">${FILEDRIVE_HOME}/plugins/transferSites/myftp.jar
${FILEDRIVE_HOME}/plugins/transferSites/myftp/lib/sftp.jar<br/></pre>
         </td>
      </tr>
   </tbody>
</table>

For more details about implementing a Custom Connector, review the examples included in SecureTransport Software Development Kit.

## Third-party libraries logging

To enable the logging, produced by third-party libraries, add a logger for a specific package in `${FILEDRIVE_HOME}/conf/tm-log4j.xml`.

For example:

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When you are deploying your Custom Connector implementation, you should only include third party dependencies used by your implementation. You should not add APIs provided run-time by <span>SecureTransport</span>. This includes the <span>SecureTransport</span> Pluggable Transfer Site SPI, Bean Validation API, and JSR-330 (<code>javax.inject</code>) API.         </td>
      </tr>
</table>

 

Third-party libraries loggers don't need any additional inclusion of logging libraries like `SLF4J, Log4j or JUL (java.util.logging)`. They will be loaded if needed, like any existing library in SecureTransport (`${FILEDRIVE_HOME}/lib/jar`). All SecureTransport libraries will be loaded with priority in case of any duplicated libraries in plug-ins directory.  

For more information about the deployment of custom site connectors, refer to [Deploy a custom protocol connector](#).  

## Expression language support

Expression evaluator service will evaluate expressions that follow the supported expression language (EL). More detailed information about the Expression Language support in SecureTransport can be found in SecureTransport Administrator’s Guide (*Appendix H: Expression Language*). The following sub-sections is applicable for the expression evaluator service:

1.  Expression Language operators
2.  Predefined variables
    -   `${uploadFolderOverwrite}` – this variable will hold value from the Overwrite Upload Folder field in the Send To Partner step. If the value is not present, an empty string will be returned.
    -   `${timestamp}` – the timestamp variable in Unix Epoch time
3.  Predefined functions
4.  Match and replace functions.
