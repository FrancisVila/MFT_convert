{
    "title": "Transfer acceleration ",
    "linkTitle": "Transfer acceleration ",
    "weight": "340"
}To enable acceleration set the uconf values as recommended in this section.

## About transfer acceleration

**UNIX/Windows only**

The Transfer CFT acceleration feature offers significantly faster transfer rates for large-file transfers, traveling long-distances over high bandwidth networks.

Transfer CFT achieves this transfer acceleration using two methods:

-   UDT: a UDP-based protocol (User Datagram Protocol)
-   pTCP: parallel TCP, which uses multiple parallel connections

### UDT description

UDT is a transport protocol that Transfer CFT can use to manage applications over high-speed networks. UDT uses UDP, a lower layer message, to transfer bulk data.

## Configuring accelerated communication

To enable accelerated communication in CFTUTIL use the unified configuration command UCONFSET.

### Basic configuration

You can globally enable or disable the acceleration function in the Transfer CFT unified configuration. Next, indicate the network resources that you want to have accelerated by UDT and pTCP.

#### Parameters

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>acceleration.enable         </td>
         <td>Activate/deactivate the acceleration option.         </td>
      </tr>
      <tr>
         <td>acceleration.udt         </td>
         <td>UDT default peer definition.         </td>
      </tr>
      <tr>
         <td>acceleration.ptcp         </td>
         <td>pTCP default peer definition.         </td>
      </tr>
   </tbody>
</table>

#### Example in CFTUTIL

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><span>CFTUTIL UCONFSET ID=acceleration.enable, VALUE=yes</span>
<br/><span>CFTUTIL UCONFSET ID=acceleration.udt   ,    VALUE=NET1</span>
<br/><span>CFTUTIL UCONFSET ID=acceleration.ptcp  ,   VALUE=NET0 NET_TEST</span>
         </td>
      </tr>
   </tbody>
</table>

In this example, all protocols (CFTPROT objects) using NET1 are accelerated by UDT, and those using NET0 and NET\_TEST are accelerated by pTCP.

Network resources that are scheduled to use acceleration functionality should have their own class number in order to avoid conflicts with other network resources, one for UDT and another for pTCP. In example above, NET1 could have a class number of 4, and NET0 and NET\_TEST could have a class number of 5. Additionally, partners using these network resources should also have the same class number as corresponding NET.

**Example**

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTNET ID=NET0,CLASS=4,...
</p>
            <p>CFTNET ID=NET1,CLASS=5,...
</p>
            <p> </p>
            <p>
CFTPROT ID=PESITANY,TYPE=PESIT,NET=NET1,SAP=1761,...
</p>
            <p>CFTPROT ID=PESITSSL,TYPE=PESIT,NET=NET0,SAP=1762,SSL=SSLSERVER,...

</p>
            <p> </p>
            <p>CFTPART ID=PART1,PROT=PESITANY,sap=part1_remote_sap... 
</p>
            <p>CFTTCP ID=PART1,host=@part1,CLASS=5,...

</p>
            <p> </p>
            <p>CFTPART ID=PART0,PROT=PESITSSL,sap=part0_remote_sap...
</p>
            <p>CFTTCP ID=PART0,host=@part0,CLASS=4,...

</p>
            <p> </p>
            <p>CFTPART ID=PART2,PROT=PESITANY,sap=part2_remote_sap...
</p>
            <p>CFTTCP ID=PART2,host=@part2,CLASS=1,...


</p>
            <p> </p>
         </td>
      </tr>
   </tbody>
</table>

**Results**

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTUTIL SEND PART=PART1,IDF=T1 will execute a transfer using "PESIT ANY" protocol and UDT network protocol
</p>
            <p>CFTUTIL SEND PART=PART0,IDF=T2 will execute a transfer using "PESIT ANY" protocol with SSL and PTCP network protocol
</p>
            <p>CFTUTIL SEND PART=PART2,IDF=T3 will fail with the following message : "CFTT11E PART=PART2 PROT=PESITANY </p>
            <p>CLASS=5 _ CFTTCP not found"</p>
         </td>
      </tr>
   </tbody>
</table>

### Advanced configuration parameters

Additional attribute parameters are available for advanced users. The default values should be adequate for most use cases. The following example shows a configuration for the unified configuration dictionary.

#### UDT parameters

Refer to the [UCONF parameters](../uconf_directory) table acceleration.udt.&lt;logicalID>.

#### pTCP parameters

Refer to the [UCONF parameters](../uconf_directory) table acceleration.ptcp.&lt;logicalID>.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>Transfer CFT</span> versions that use the newer pTCP protocol cannot perform pTCP exchanges with  <span>Transfer CFT</span>s using the earlier pTCP version. See <a href="../uconf_protocols_and_networks">Protocols and networks</a> for more information.         </td>
      </tr>
</table>

## <span id="uconf_ptcp"></span>pTCP protocol versions

Transfer CFT 3.0.1 SP2 and higher, and Transfer CFT 2.7.1 SP6, support a more recent version of the pTCP protocol than previously supported by Transfer CFT. This newer version of pTCP offers the following advantages:

-   Multi-node architecture support
-   Exchange capability with Axway SecureTransport

Note that the new pTCP support is not compatible with the previously used version of pTCP. This means that Transfer CFT 3.0.1 SP2 and higher, and Transfer CFT 2.7.1 SP6, cannot exchange files with earlier versions of Transfer CFT using the pTCP protocol.

For more information on supported platforms and transfer acceleration, refer to [Platform-specific functionality](platform_specific_functionality.htm).

Related topics

-   [About the unified configuration](..//transfercft/admin_intro/uconf)
-   [Unified configuration (CFTUTIL)](../uconf_w_cftutil)
