{
    "title": "Applications ",
    "linkTitle": "Applications",
    "weight": "90"
}{{< Gateway/componentlongname  >}}: Overview

As described in the [previous topic](../ov_transfer_sites), a file transfer occurs between two or more computers. Gateway recognizes the computers involved in a transfer via information stored in Site objects. To successfully transfer a file, Gateway also requires information describing the format of the file that is the object of the transfer.

<span id="application_object"></span>

### Application object

For some transfers, the applications that process the transferred file on the sending and receiving machines cannot handle files of the same format. If this is the case, you can create an *Application object* in which you specify the differences between the attributes of the file as it resides on your local machine, and the file that is transferred. Gateway then uses this information to transform the format of the transferred file.

You can enter the following types of information in an Application object:

-   Local file system attributes such as name, file structure and type
-   Record format
-   Data encryption and padding
-   Online record attributes
-   Compression mode

### Example

Gateway receives a file via the PeSIT protocol from an Axway Transfer product hosted on an MVS platform. An FTP client on a Windows platform then requests the transfer of the file from Gateway.

<img src="/Images/Gateway/Appli_756x351.png" class="mediumWidth" />

The file that Axway Transfer deposits to Gateway has the following characteristics:

-   Record format: stream
-   Record length: 180
-   Data code: EBCDIC

The FTP client handles files with the following characteristics:

-   Record format: Variable text
-   Record length: 1024
-   Data code: ASCII

You create an Application object that specifies the characteristics of the file as it is deposited to Gateway, and as it must be received by the FTP client. In the Transfer Request for the delivery to the FTP client you specify this Application object.

During the transfer process, Gateway transforms the file to the format required by the FTP client.

## Specifying file characteristics for Transfers

When you have created an Application object for a specific type of transfer, you can then link the Application to the Transfer when you create the Transfer Request. The Application that you link must belong to the same group as the Site that you specify in the **Destination alias** field of the Transfer Request. By default, when you create new Sites and Applications, the group value is set to GDEFAULT.

It is not necessary to link an Application to every Transfer Request. There are two alternative ways that you can provide Gateway with application file system information for a Transfer:

-   <span style="font-weight: bold;">Explicitly enter file information in the Transfer Request</span>  
    You can enter information about file format directly in the Transfer Request in the <span style="font-weight: bold;">Attributes</span> tab. Then, if you do not specify an Application in the Transfer Request, Gateway takes the <span style="font-weight: bold;">Attributes</span> tab values. In this case, you must specify the Record format and the Record length.

<!-- -->

-   <span style="font-weight: bold;">Enter the file format information in a Model</span>  
    You can enter values for file format attributes in a Model object. You then attach the Model to the Transfer Request. Gateway then takes the values from the Model object.  
    If you set the same parameters in both the Transfer Request and the Model objects, the Transfer Request parameters override the parameters set in the Model.

## Default Applications

Gateway provides a set of default Applications. When Gateway operates in Responder mode, it assigns an Application to the incoming transfer as follows:

-   <span style="font-weight: bold;">PeSIT transfers</span>: The Application name is the incoming protocol filename. The default Application names are DEFAULT\_B (Binary), DEFAULT\_A (ASCII) and DEFAULT\_E (EBCDIC), depending on the type of data to be transferred. If Gateway cannot find the required Application (from those listed above), it uses the Application DEFAULT.
-   <span style="font-weight: bold;">FTP/SFTP transfers</span>: The client station can define Application names with an FTP <span class="code">SITE</span> command before sending the <span class="code">STOR</span> or the <span class="code">RETR</span> command. The default Application names are FTP\_B (Binary), FTP\_A (ASCII) and FTP\_E (EBCDIC) depending on the FTP data type. Since ASCII and EBCDIC are meaningless in SFTP, SFTP transfers use the default Application FTP\_B.
-   <span style="font-weight: bold;">HTTP transfers</span>: Since the client station does not provide the Application name, Gateway uses the default FTP Application for file reception.

[Next topic](../ov_connection_gates)

Related topics

[About Applications](../../transfers_start_here/parameters_start_here/applications_start_here)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
