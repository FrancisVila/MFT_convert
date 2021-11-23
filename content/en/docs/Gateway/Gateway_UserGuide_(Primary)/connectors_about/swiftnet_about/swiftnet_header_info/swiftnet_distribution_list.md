{
    "title": "SWIFTNet Distribution List",
    "linkTitle": "SWIFTNet Distribution List",
    "weight": "300"
}{{< Gateway/componentlongname  >}}: Connectors

[Overview](#Overview)

[Specifying parameters](#specifying_paras)

[End of transfer parameters](#End_of_transfer_paras)

[GikAPI parameters](#GikAPI)

[XML file structure](#XML_File_structure)

[Examples](#examples)

<span id="Overview"></span>

## Overview

This topic describes SWIFTNet Distribution List (distribution to multiple recipients).

SWIFT supports the possibility to send the same message or file to multiple recipients in one single transaction.

### When Gateway acts as Initiator

Gateway enables you to send InterAct SnF messages, or FileAct SnF transfers,to several recipients in a single transaction.

Gateway allows other applications to specify the list of recipients with the help of an input XML file. The XML document must be well-formed and have a specific format. Gateway makes sure that what has been requested is consistent with the content of the exchange request. If it is not, it adds the necessary information or rejects the exchange request and generates an error message.

The same file or message cannot be sent several times to the same recipient. The recipient list should only contain unique entries.

Additionally, you can specify whether or not the responder can receive the list of recipients by using the `sw_public_recipient_list_ind` parameter in either the Transfer Request or the Trading Partner.

Like non-distributed SnF traffic, Gateway receives positive or failed delivery notifications. These delivery notifications are however always received as system messages. According to the receipt option, Gateway can receive as many system message delivery notifications or failed delivery notifications as the number of specified recipients.

To be able to send a distributed file or message, you need to create a remote Trading Partner with the trade name (**Name**) "cn=distributor,o=swift,o=swift". The service (**Service name**) and request type (**Request type**) have the same significance as for normal remote Trading Partners.

To receive non-delivery warning, delivery notification or failed delivery notification system messages, you need a Trading Partner that allows the reception of these system message types. For information about the default Trading Partner used to receive system messages, refer to [SYSTEM\_MESSAGES remote Trading Partner](../../swiftnet_connector/swiftnet_configuring#sys_messages_tp). For information about request type values associated with different system message types, refer to the SWIFTNet documentation.

### When Gateway acts as Responder

There is no significant difference between the reception of distributed and non-distributed files or messages.

If the sender specifies that the recipient list is public, Gateway saves this list in a file and signals its presence so that upper applications can then carry out additional processing.

<span id="specifying_paras"></span>

## Specifying parameters

### Transfer Request parameters

#### Additional params

Reference to a file on the disk containing Recipient List, HeaderInfo or SignatureList information.

Use the **Additional params** parameter to specify the file. The file must respect a specific structure, as described in "XML File structure" later in this topic.

peltrans  -sw\_add\_params (-swaddpar)  &lt;file reference to additional SWIFTNet structures>

<span id="End_of_transfer_paras"></span>

## End of transfer parameters

The following end of transfer parameters are available:

<span class="code">x\_sw\_add\_params</span> = &lt;Reference to a file on disk where Signature List and/or Header Info and/or Additional parameters are stored>

#### Example

x\_sw\_add\_params='d:\\builds\\gtw6120dev\\srvinstall\\run\_time\\tmp\\SW000001.xml'

<span id="GikAPI"></span>

## GikAPI parameters

The following parameter can be found in the <span class="code">gikapic.h</span> header:

-   GIK\_T\_SW\_ADD\_PARAMS            385   /\* String \*/

<span id="XML_File_structure"></span>

## XML file structure

Refer to the XML schemas (<span class="code">.xsd</span> files) supplied with Gateway for examples of file structure. You can use the <span class="code">AddSwParams.xsd</span> file to create or validate XML files for Recipient List, HeaderInfo and SignatureList information usage. The <span class="code">.xsd</span> files are located in:

&lt;Gateway installation directory>/run\_time/swnet

### Typical XML file with Recipient List


    <AddSwParams>
       <SwRecipientList xmlns:Sw="urn:swift:snl:ns.Sw">
          <Out>
          <Sw:RecipientList>
             <Sw:RecipientDN>
             cn=recipient1,ou=fr,o=bankfrpp,o=swift
             </Sw:RecipientDN>
             <Sw:RecipientDN>
             cn=recipient2,ou=fr,o=bankfrpp,o=swift
             </Sw:RecipientDN>
             <Sw:RecipientDN>
             cn=recipient3,ou=fr,o=bankfrpp,o=swift
             </Sw:RecipientDN>
          </Sw:RecipientList>
          </Out>
       </SwRecipientList>
    </AddSwParams>

<span id="examples"></span>

## Examples

For examples of files containing SWIFTNet Recipient List information, refer to [SWIFTNet dump to XML](../../swiftnet_backup_sites/swiftnet_dump_to_xml).

Related topics

[SWIFTNet connector](../../swiftnet_connector)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../../swiftnet_connector/swiftnet_configuring)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet](../../swiftnet_connector/swiftnet_working_with)

[New Transfer Request: SWIFTNet tab](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_swiftnet_tab)

[SWIFTNet File and Message Copy](../swiftnet_file_copy)

[SWIFTNet dump to XML](../../swiftnet_backup_sites/swiftnet_dump_to_xml)

[About C API](../../../../customizing_gw_about/c_api_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
