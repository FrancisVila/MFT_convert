{
    "title": "SWIFTNet Signature List",
    "linkTitle": "Security & availability",
    "weight": "290"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[Overview](#Overview)

[Specifying parameters](#specifying_paras)

[End of transfer parameters](#End_of_transfer_paras)

[GikAPI parameters](#GikAPI)

[XML file structure](#XML_File_structure)

[Examples](#examples)

<span id="Overview"></span>

## Overview

This topic describes the SWIFTNet Signature List feature (new paradigm for signing).

Signing is possible using two paradigms: Crypto or SignatureList. If signing is requested and there is reference to a SignatureList file, Gateway uses the SignatureList paradigm. Otherwise Gateway signs the message using Crypto.

#### When Gateway acts as Initiator

Gateway enables you to sign InterAct RT and SnF messages, and FileAct RT and SnF transfers, exchanged over the SWIFT network using SignatureList for signing. The SignatureList paradigm secures a message digest of the information that needs to be secured instead of signing the information itself (as done when using Crypto).

Gateway allows other applications to specify what needs to be signed with the help of an input XML file. The XML document must be well-formed and have a specific format. Gateway makes sure that what has been requested is consistent with the content of the exchange request. If it is not, it adds the necessary information or rejects the exchange request and generates an error message.

#### When Gateway acts as Responder

As a responder, Gateway saves the secured data information received from the initiator in a file and signals its presence so that backend applications can then carry out validation checks. In the first step, SNL automatically verifies the incoming secured data. Backend applications need to complete this process by verifying that the DigestValue of an application-specific reference matches the information that is digested.

Gateway also offers the possibility to secure the responses using the same SignatureList signing paradigm.

<span id="specifying_paras"></span>

## Specifying parameters

If you request signing and you specify a SignatureList file, Gateway uses the SignatureList paradigm. Otherwise Gateway signs the message using Crypto. You must use the same signing option (Crypto or Signature List) at the sender side *and* the receiver side.

### Requesting signature

**On the sender side:** Request signing in the Transfer Request (using the **Sign** or <span class="code">trade\_sign</span> parameter) or the Trading Partner (using the **Sign** parameter).

**On the receiver side:** Request signing in the Trading Partner (using the **Sign** parameter). The signing parameters are used in generating the response for the received request.

The service profile (defined by SWIFT) determines whether signing on sender requests / receiver responses is optional or mandatory.

### Specifying the Signature List file

Gateway offers two ways of specifying the Signature List file:

-   Per transfer (in the Transfer Request)
-   For all transfers exchanged with a specific partner (in the Trading Partner). When Gateway accepts requests through this Trading Partner then the Signature List file is used to sign the responses sent back to SWIFT.

When sending or receiving an ACK, the presence of a Signature List file at the Trading Partner level ensures that the ACK Request/Response is signed with the default SWIFT digest references.

You cannot use the same Signature List file for signing both the request and the response (as they have different default SWIFT digest references) from the Trading Partner level. If you use the same Trading Partner both for sending and receiving, you must specify a Signature List file when submitting outgoing requests. The Signature List file from the Trading Partner is used to sign the responses.

### Transfer Request parameters

The following parameters are references to files with the same internal structure. The file must respect a specific structure, as described in "XML File structure" later in this topic.

If you have both HeaderInfo and SignatureList in the same file, and you want to use them both, use the <span style="font-weight: bold;">Additional params</span> parameter to specify the file. If you only want to use SignatureList information from the file, use the <span style="font-weight: bold;">Signature list</span> parameter.

#### Signature list

Reference to a file on the disk containing a Signature List.

peltrans  -sign\_list (-signl)  &lt;file reference to signature list>

#### Additional params

Reference to a file on the disk containing SignatureList, HeaderInfo or Recipient List.

peltrans  -sw\_add\_params (-swaddpar)  &lt;file reference to additional SWIFTNet structures>

### Trading Partner parameter

#### Signature List

Reference to a file on the disk containing a Signature List.

peladm create\_tradepart ? | grep sign\_list

              -sign\_list (-signl)  &lt;file reference to signature list>

<span id="End_of_transfer_paras"></span>

## End of transfer parameters

The following end of transfer parameters are available:

<span class="code">x\_sw\_add\_params</span> = &lt;Reference to a file on disk where Signature List and/or Header Info and/or Additional parameters are stored>

x\_sign\_list = Y / N

#### Examples

x\_sw\_add\_params='d:\\builds\\gtw6120dev\\srvinstall\\run\_time\\tmp\\SW000001.xml'

x\_sign\_list='Y'

<span id="GikAPI"></span>

## GikAPI parameters

The following parameters can be found in the <span class="code">gikapic.h</span> header:

-   GIK\_T\_SW\_SIGN\_LIST             384   /\* String \*/
-   GIK\_T\_SW\_ADD\_PARAMS            385   /\* String \*/

<span id="XML_File_structure"></span>

## XML file structure

Refer to the XML schemas (<span class="code">.xsd</span> files) supplied with Gateway for examples of file structure. You can use the <span class="code">AddSwParams.xsd</span> file to create or validate XML files for SignatureList, HeaderInfo and Recipient List usage. The <span class="code">.xsd</span> files are located in:

&lt;Gateway installation directory>/run\_time/swnet

### Typical XML file with SignatureList


    <AddSwParams>
       <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
          <Out> ...
          </Out>
          <In> ...
          </In>
       </SwSignatureList>
    </AddSwParams>

### Support for different SwSec:SignDNs in the XML file

There may be cases where you want to use a single Signature List file to sign the messages exchanged with a specific Trading Partner (defined at the Trading Partner level). However, the messages can be exchanged through two different Remote Sites with two different principals (SecurityContext UserDNs).

In this case, you can use the joker string "AnyDN" for SwSec:SignDN. The DN will then be the principal from the active (used) Remote Site.

For more information, refer to [Working with signed or encrypted messages](../swiftnet_connector/swiftnet_configuring#signed_or_encrypted_messages) in the *Configuring the* <span class="mc-variable axway_variables.Component_Long_Name variable" style="font-style: italic;">Axway Gateway</span>*/SWIFTNet environment* topic.

<span id="examples"></span>

## Examples

For examples of files containing SWIFTNet Signature List information, refer to [SWIFTNet dump to XML](../swiftnet_backup_sites/swiftnet_dump_to_xml).

Related topics

[SWIFTNet connector](../swiftnet_connector)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../swiftnet_connector/swiftnet_configuring)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet](../swiftnet_connector/swiftnet_working_with)

[New Transfer Request: SWIFTNet tab](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_swiftnet_tab)

[Transfers: Parameters List](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list)

[SWIFTNet dump to XML](../swiftnet_backup_sites/swiftnet_dump_to_xml)

[About C API](../../../customizing_gw_about/c_api_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
