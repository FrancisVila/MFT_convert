{
    "title": "UCONF: Transfer acceleration",
    "linkTitle": "Transfer acceleration",
    "weight": "310"
}To enable acceleration set the uconf values as recommended in this section.

## About transfer acceleration

**UNIX/Windows only**

The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> acceleration feature offers significantly faster transfer rates for large-file transfers, traveling long-distances over high bandwidth networks.

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> achieves this transfer acceleration using two methods:

-   UDT: a UDP-based protocol (User Datagram Protocol)
-   pTCP: parallel TCP, which uses multiple parallel connections

### UDT description

UDT is a transport protocol that <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can use to manage applications over high-speed networks. UDT uses UDP, a lower layer message, to transfer bulk data.

## Configuring accelerated communication

To enable accelerated communication in CFTUTIL use the unified configuration command <span class="code">UCONFSET</span>.

### Basic configuration

You can globally enable or disable the acceleration function in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> unified configuration. Next, indicate the network resources that you want to have accelerated by UDT and pTCP.

#### Parameters

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Description         </th>
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


    CFTUTIL UCONFSET ID=acceleration.enable, VALUE=yes

    CFTUTIL UCONFSET ID=acceleration.udt   ,    VALUE=NET1

    CFTUTIL UCONFSET ID=acceleration.ptcp  ,   VALUE=NET0 NET_TEST

In this example, all protocols (CFTPROT objects) using NET1 are accelerated by UDT, and those using NET0 and NET\_TEST are accelerated by pTCP.

Network resources that are scheduled to use acceleration functionality should have their own class number in order to avoid conflicts with other network resources, one for UDT and another for pTCP. In example above, NET1 could have a class number of 4, and NET0 and NET\_TEST could have a class number of 5. Additionally, partners using these network resources should also have the same class number as corresponding NET.

**Example**



    CFTNET ID=NET0,CLASS=4,...

    CFTNET ID=NET1,CLASS=5,...

     

    CFTPROT ID=PESITANY,TYPE=PESIT,NET=NET1,SAP=1761,...

    CFTPROT ID=PESITSSL,TYPE=PESIT,NET=NET0,SAP=1762,SSL=SSLSERVER,...

     
    CFTPART ID=PART1,PROT=PESITANY,sap=part1_remote_sap... 

    CFTTCP ID=PART1,host=@part1,CLASS=5,...

     
    CFTPART ID=PART0,PROT=PESITSSL,sap=part0_remote_sap...

    CFTTCP ID=PART0,host=@part0,CLASS=4,...

     
    CFTPART ID=PART2,PROT=PESITANY,sap=part2_remote_sap...

    CFTTCP ID=PART2,host=@part2,CLASS=1,...


     

**Results**



    CFTUTIL SEND PART=PART1,IDF=T1 will execute a transfer using "PESIT ANY" protocol and UDT network protocol

    CFTUTIL SEND PART=PART0,IDF=T2 will execute a transfer using "PESIT ANY" protocol with SSL and PTCP network protocol

    CFTUTIL SEND PART=PART2,IDF=T3 will fail with the following message : "CFTT11E PART=PART2 PROT=PESITANY 
    CLASS=5 _ CFTTCP not found"

### Advanced configuration parameters

Additional attribute parameters are available for advanced users. The default values should be adequate for most use cases. The following example shows a configuration for the unified configuration dictionary.

#### UDT parameters

Refer to the [UCONF parameters](../../../admin_intro/uconf/uconf_directory) table <span class="code">acceleration.udt.&lt;logicalID></span>.

#### pTCP parameters

Refer to the [UCONF parameters](../../../admin_intro/uconf/uconf_directory) table <span class="code">acceleration.ptcp.&lt;logicalID></span>.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> versions that use the newer pTCP protocol cannot perform pTCP exchanges with <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s using the earlier pTCP version. See <a href="../../../admin_intro/uconf/uconf_protocols_and_networks">Protocols and networks</a> for more information.         </td>
      </tr>
   </tbody>
</table>

<span id="uconf_ptcp"></span>

## pTCP protocol versions

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> 3.0.1 SP2 and higher, and <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> 2.7.1 SP6, support a more recent version of the pTCP protocol than previously supported by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>. This newer version of pTCP offers the following advantages:

-   Multi-node architecture support
-   Exchange capability with Axway SecureTransport

Note that the new pTCP support is <span class="bold_in_para">not </span>compatible with the previously used version of pTCP. This means that <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> 3.0.1 SP2 and higher, and <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> 2.7.1 SP6, <span class="bold_in_para">cannot </span>exchange files with earlier versions of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> using the pTCP protocol.

For more information on supported platforms and transfer acceleration, refer to Platform-specific functionality.

Related topics

-   [About the unified configuration](../../../admin_intro/uconf)
-   [Unified configuration (CFTUTIL)](../../../admin_intro/uconf/uconf_w_cftutil)