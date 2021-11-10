{
    "title": "SWIFTNet Header Info",
    "linkTitle": "Special transfer patterns",
    "weight": "280"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[Overview](#Overview)

[Specifying parameters](#specifying_paras)

[End of transfer parameters](#End_of_transfer_paras)

[GikAPI parameters](#GikAPI)

[XML file structure](#XML_File_structure)

[Examples](#examples)

<span id="Overview"></span>

## Overview

You can use the enhanced FileAct header structure (HeaderInfo field) to send additional business-related header information such as payment instructions through FileAct. This is useful if you use service profiles like Transaction Count and Payment File Summary. Gateway makes a validation to ensure the content is consistent with the data and meta-data being transported.

When acting as a Responder, Gateway saves the HeaderInfo structure, if present, in a file and signals its presence so that upper applications can carry out additional processing. For FileAct RT GET transfers, Gateway also offers the possibility to put such information in the E2EControl.

<span id="specifying_paras"></span>

## Specifying parameters

### Transfer Request parameters

The following parameters are references to files with the same internal structure. The file must respect a specific structure, as described in "XML File structure" later in this topic.

If you have both HeaderInfo and SignatureList in the same file, and you want to use them both, use the <span style="font-weight: bold;">Additional params</span> parameter to specify the file. If you only want to use the HeaderInfo information from the file, use the <span style="font-weight: bold;">Header info</span> parameter.

#### Header info

Reference to a file on the disk containing HeaderInfo.

peltrans  -header\_info (-hinf)  &lt;file reference to header info structure>

#### Additional params

Reference to a file on the disk containing HeaderInfo, SignatureList or Recipient List.

peltrans  -sw\_add\_params (-swaddpar)  &lt;file reference to additional SWIFTNet structures>

<span id="End_of_transfer_paras"></span>

## End of transfer parameters

The following end of transfer parameters are available:

<span class="code">x\_sw\_add\_params</span> = &lt;Reference to a file on disk where Header Info and/or Signature List and/or Additional parameters are stored>

x\_header\_info = Y / N

#### Examples

x\_sw\_add\_params='d:\\builds\\gtw6120dev\\srvinstall\\run\_time\\tmp\\SW000001.xml'

x\_header\_info='N'

<span id="GikAPI"></span>

## GikAPI parameters

The following parameters can be found in the <span class="code">gikapic.h</span> header:

-   GIK\_T\_SW\_HEADER\_INFO           383   /\* String \*/
-   GIK\_T\_SW\_ADD\_PARAMS            385   /\* String \*/

<span id="XML_File_structure"></span>

## XML file structure

Refer to the XML schemas (<span class="code">.xsd</span> files) supplied with Gateway for examples of file structure. You can use the <span class="code">AddSwParams.xsd</span> file to create or validate XML files for HeaderInfo, SignatureList and Recipient List usage. The <span class="code">.xsd</span> files are located in:

&lt;Gateway installation directory>/run\_time/swnet

### Typical XML file with HeaderInfo


    <AddSwParams>
       <SwHeaderInfo>
          <Out> ...
          </Out>
          <In> ...
          </In>
       </SwHeaderInfo>
    </AddSwParams>

<span id="examples"></span>

## 

## Adding more HeaderInfo fields

It is possible to extend HeaderInfo support with additional HeaderInfo fields.

Gateway, by default, supports the following HeaderInfo fields:

-   Payment File Summary (<span class="code">ApplSpcfc.PmtSummry.01</span>)
-   Transaction Count (<span class="code">ApplSpcfc.TxsCntr.01</span>)
-   Trade Files (<span class="code">ApplSpcfc.Trade.01</span>)
-   Bank Account Management Files (<span class="code">ApplSpcfc.BAM.01</span>)

The HeaderInfo data (specified when creating a transfer) is validated against an XML schema consisting on a master schema (<span class="code">AddSwParams.xsd</span>) and several element schemas.

Adding a new HeaderInfo element schema requires the following operations:

-   add the corresponding .xsd file (e.g. <span class="code">ApplSpcfc.NewSchema.01.xsd</span>) in the <span class="code">run\_time/swnet </span>directory
-   alter the <span class="code">AddSwParams.xsd </span>file to include the new schema:
    -   add a <span class="code">namespace </span>entry, for example:  
        &lt;xs:import namespace="urn:swift:xsd:ApplSpcfc.NewSchema.01" schemaLocation="ApplSpcfc.NewSchema.01.xsd"/>
    -   add the corresponding <span class="code">xs:element </span>entry into the HeaderInfo <span class="code">xs:complexType</span>, for example:  
        &lt;xs:element xmlns="urn:swift:xsd:ApplSpcfc.NewSchema.01" ref="ApplSpcfc" minOccurs="0" maxOccurs="1"/>

> **Note:**
>
> Make sure the added element schemas are well formed, and that the changes in AddSwParams are correct - an incorrect schema will impact the product functionality. Prior validation with an external XML tool is recommended.

> **Note:**
>
> The same mechanism is used to validate other AddSwParams elements: Signature Lists, System Messages, ProductInfo Lists, ThirdParty and Recipient DN Lists and so on. Please do not remove any element of the XML schemas.

> **Note:**
>
> Consult the SWIFTNet Standards before extending HeaderInfo support to new fields. This should be done only for SWIFTNet Standards-compliant fields not included by a default Gateway installation.

## Examples

For examples of files containing SWIFTNet Header Info, refer to [SWIFTNet dump to XML](../swiftnet_backup_sites/swiftnet_dump_to_xml).

Related topics

[SWIFTNet connector](../swiftnet_connector)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../swiftnet_connector/swiftnet_configuring)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet](../swiftnet_connector/swiftnet_working_with)

[New Transfer Request: SWIFTNet tab](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_swiftnet_tab)

[SWIFTNet File and Message Copy](swiftnet_file_copy)

[SWIFTNet dump to XML](../swiftnet_backup_sites/swiftnet_dump_to_xml)

[About C API](../../../customizing_gw_about/c_api_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
