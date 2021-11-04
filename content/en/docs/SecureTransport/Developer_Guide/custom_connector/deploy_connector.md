{
    "title": "Deploy a custom protocol connector",
    "linkTitle": "Deploy a custom protocol connector",
    "weight": "110"
}In order to configure and deploy a Custom Connector implementation into <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server, follow these steps:

1.  After implementing Custom Connector and the User Interface for this connector you should add them to a single jar file. For Site SPI version 1.0, you must create a `MANIFEST.MF` file in the jar file that describes the integration points between <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and the Custom Connector.  
    The `META-INF/MANIFEST.MF` file must be created with the following properties:  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Property         </th>
    <th class="HeadD-Column1-Header1">Description         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td>Custom-Protocol         </td>
             <td><p>The name of the protocol as displayed in SecureTransport File Tracking. File Tracking also logs the protocol. Should be unique. Maximum of 255 characters.</p>         </td>
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
             <td>The full name of the class that extends the <code>com.axway.st.plugins.site.CustomSite</code> abstract class and implements the <code>com.axway.st.plugins.site.Connection</code> interface. This is the integration point between <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and the Custom Transfer Site.         </td>
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

      
    This metadata file is used by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to register and use the Custom Connector implementation like a regular Transfer Site.  
    If your Custom Connector implementation depends on third party libraries, you have two implementation approaches:
    -   You can use a fat jar file that stores your classes and the classes from all dependent jars into a one single jar file.
    -   or

    <!-- -->

    -   Add a Class-Path attribute to the `MANIFEST.MF` file, in which you should enumerate your dependent jars separated by spaces or tabs. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> will add the enumerated libraries to the Custom Connector implementation classpath.

    -   For Site SPI v1.1 or higher use instead the `Plugin-Info.yaml` file.  
        The META-INF/Plugin-Info.yaml must be created with the same properties as described above.  
        Example:

    -   Custom-Protocol: myProtocol
            SPI-Version: '1.0':
            Custom-Site: com.axway.st.plugins.site.MyProtocol_1_0
            Protocol-Label: My Sample Transfer Site (1.0)
            Custom-UI: html/mySite-1-0.html
            Class-Path: MySite/lib/lib1.jar MySite/lib/lib2.jar MySite/lib_1_0/lib3_1_0.jar
            '1.1':
            Custom-Site: com.axway.st.plugins.site.MyProtocol_1_1
            Protocol-Label: My Sample Transfer Site (1.1)
            Custom-UI: html/mySite-1-1.html
            Class-Path: MySite/lib/lib1.jar MySite/lib/lib2.jar MySite/lib_1_1/lib3_1_1.jar
2.  Deploy Custom Connector into <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>.

When you have produced/created a jar file containing the Custom Connector implementation and a `MANIFEST.MF` file, you should place it into your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server. In the installation folder of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> 5.3.6 version and above, you will find the following directory:

-   `${FILEDRIVE_HOME}/plugins/transferSites`, where `${FILEDRIVE_HOME}` represents <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation directory.

> **Note:**
>
> In a cluster environment, you must add the Custom Connector jar file to all nodes of the cluster.

The Custom Connector jar file should be placed in the `${FILEDRIVE_HOME}/plugins/transferSites` directory. This directory is scanned by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> for jar files with the specific `MANIFEST.MF` file describing the integration points between the custom connector and the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server. For each custom connector, there should be a jar file containing the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Pluggable Transfer Site SPI implementation and the `MANIFEST.MF` file. Also, if there are any third party resources that are required by your custom connector implementation and are not included in the Custom Connector jar, they should be placed in a separate directory inside the `${FILEDRIVE_HOME}/plugins/transferSites` directory and be listed in the `MANIFEST.MF` file under Class-Path attribute.

> **Note:**
>
> External libraries should be placed in separate directory inside the ${FILEDRIVE\_HOME}/plugins/transferSites directory.

Let's assume you have already implemented the simple FTP Custom Connector with a third party dependencies to external library named `sftp.jar`. Then the `MANIFEST.MF` file should look like this:


    Custom-Protocol: myftp
    Protocol-Label: FTP(S) Sample Transfer Site
    Custom-UI: ftpSampleSite.html
    Custom-Site: com.axway.st.plugins.site.sdk.ftp.FTPSite
    Class-Path: myftp/lib/sftp.jar

Аdd your Custom Connector implementation jar to the `${FILEDRIVE_HOME}/plugins/transferSites/` directory and the `sftp.jar` file to the `${FILEDRIVE_HOME}/plugins/transferSites/lib/myftp/lib/` directory inside the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation directory. The final directory structure should look like this:


    ${FILEDRIVE_HOME}/plugins/transferSites/myftp.jar
    ${FILEDRIVE_HOME}/plugins/transferSites/myftp/lib/sftp.jar

After your custom connector jar file, including the third party libraries, is placed in the `${FILEDRIVE_HOME}/plugins/transferSites` directory, the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Service should be restarted in order to load and register your Custom Connector implementation as a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Transfer Site.

> **Note:**
>
> When you are deploying your Custom Connector implementation, you should only include third party dependencies used by your implementation. You should not add APIs provided run-time by SecureTransport. This includes the SecureTransport Pluggable Transfer Site SPI, Bean Validation API, and JSR-330 (javax.inject) API.

For more details about implementing a Custom Connector, review the examples included in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Software Development Kit.

## Third-party libraries logging

To enable the logging, produced by third-party libraries, add a logger for a specific package in `${FILEDRIVE_HOME}/conf/tm-log4j.xml`.

For example:



    <logger name="com.amazonaws" additivity="false">
        <level value="debug" />
        <appender-ref ref="ServerLog" />
    </logger>

 

Third-party libraries loggers don't need any additional inclusion of logging libraries like `SLF4J, Log4j or JUL (java.util.logging)`. They will be loaded if needed, like any existing library in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> (`${FILEDRIVE_HOME}/lib/jar`). All <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> libraries will be loaded with priority in case of any duplicated libraries in plug-ins directory.  

For more information about the deployment of custom site connectors, refer to <a href="#" class="MCXref xref selected">Deploy a custom protocol connector</a>.  

## Expression language support

Expression evaluator service will evaluate expressions that follow the supported expression language (EL). More detailed information about the Expression Language support in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> can be found in SecureTransport Administrator’s Guide (*Appendix H: Expression Language*). The following sub-sections is applicable for the expression evaluator service:

1.  Expression Language operators
2.  Predefined variables
    -   `${uploadFolderOverwrite}` – this variable will hold value from the Overwrite Upload Folder field in the Send To Partner step. If the value is not present, an empty string will be returned.
    -   `${timestamp}` – the timestamp variable in Unix Epoch time
3.  Predefined functions
4.  Match and replace functions.