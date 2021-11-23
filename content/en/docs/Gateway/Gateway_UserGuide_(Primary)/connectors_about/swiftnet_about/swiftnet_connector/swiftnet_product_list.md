{
    "title": "SWIFTNet ProductList",
    "linkTitle": "SWIFTNet ProductList",
    "weight": "290"
}{{< Gateway/componentlongname  >}}: Connectors

[Overview](#overview)

[Example](#example)

[Specifying the ProductList file](#specifying_paras)

[Checking file structure for XML conformity](#xml_file_structure)

[More information](#more_info)

<span id="overview"></span>

## Overview

SWIFTNet 7.0 requires the use of the ProductList XML structure. The ProductList identifies the messaging interface and backend applications used to send the message or file in generating the request or response to SWIFT.

You must provide the ProductList information for your backend application(s), including Gateway if it is used as a backend. Gateway as a messaging interface always adds itself in the ProductList. You can specify up to a maximum of three ProductInfo entries in a ProductList to specify the backend applications.

The ProductList is sent to SWIFT, but is not forwarded further to the partners. It is present in the following request/response structures:

-   SwInt:RequestControl
-   SwInt:ResponseControl
-   Sw:FileRequestControl
-   Sw:FileResponseControl
-   Sw:FetchFileRequest
-   Sw:SnFRequestControl
-   Sw:SnFResponseControl

<span id="example"></span>

## Example

Here is an example of an XML file containing ProductList information.


    <AddSwParams>
       <SwProductList xmlns:Sw="urn:swift:snl:ns.Sw">
          <Out>
             <Sw:ProductInfo>
                <Sw:VendorName>Axway</Sw:VendorName>
                <Sw:ProductName>Gateway</Sw:ProductName>
                <Sw:ProductVersion>{{< Gateway/componentversion >}}.0</Sw:ProductVersion>
             </Sw:ProductInfo>
          </Out>
       </SwProductList>
    </AddSwParams>

<span id="specifying_paras"></span>

## Specifying the ProductList file

Gateway offers two ways of specifying the ProductList file:

-   Per transfer - in the Transfer Request
-   For all transfers exchanged with a specific partner - in the Trading Partner

For outgoing flows, both methods for specifying the Product List work (Transfer Request information overrides the Trading Partner).

For incoming flows, only the Trading Partner method is available.

The file containing the ProductList information must respect a specific structure, as described in "Checking file structure for XML conformity" later in this topic.

### Transfer Request

In the Transfer Request, specify the full path of the local physical file containing ProductList information.

In the Gateway GUI, use the **Additional params** parameter on the **SWIFTNet** tab.

Alternatively, use the `peltrans` command:

peltrans  -sw\_add\_params (-swaddpar)  &lt;file reference to additional SWIFTNet structures>

### Trading Partner

In the Trading Partner, specify the full path of the local physical file containing ProductList information.

When Gateway accepts requests through this Trading Partner, the ProductList file is used to fill the responses sent back to SWIFT.

In the Gateway GUI, use the **Additional params** parameter.

<span id="xml_file_structure"></span>

## Checking file structure for XML conformity

The XML file must be well-formed and have a specific format. Refer to the XML schemas (`.xsd` files) supplied with Gateway for examples of file structure. You can use the `AddSwParams.xsd` file to validate XML files for ProductList usage. The `.xsd` files are located in:

&lt;Gateway installation directory>/run\_time/swnet

<span id="more_info"></span>

## More information

For examples of files containing SWIFTNet ProductList information, refer to the SWIFTNet official documentation.

Related topics

[SWIFTNet connector](../)

[Configuring the {{< Gateway/componentlongname  >}}/SWIFTNet environment](../swiftnet_configuring)

[Working with {{< Gateway/componentlongname  >}}/SWIFTNet](../swiftnet_working_with)

[New Transfer Request: SWIFTNet tab](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_swiftnet_tab)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
