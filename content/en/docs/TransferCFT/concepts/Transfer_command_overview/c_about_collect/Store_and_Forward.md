{
    "title": "Store  and forward ",
    "linkTitle": "Store and forward relays",
    "weight": "340"
}Store and forward, or transfer routing, allows you to define and automate file transfer using an intermediate site. This page describes using store-and-forward services either in a <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> context or using a standalone <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>.

-   [Store and forward with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>](#Store)
-   [Store and forward standalone <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>](#Store2)
    -   [Intentional
        store and forward](#Intentional_Store_and_Forward)
    -   [Intentional VAN store and forward](#Intentional_VAN_store_and_forward)
    -   [Forced
        store and forward](#Forced_Store_and_Forward)

<span id="Store"></span>

## Store and forward with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>

When implementing a <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> relay in <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>, the only relay option is the equivalent of COMMUT = YES, where a file is immediately sent to the intended final partner.

To implement a relay in conjunction with <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>:

1.  Create the flow as described in the [Central Governance User Guide](https://docs.axway.com/bundle/CentralGovernance_113_UsersGuide_allOS_en_HTML5/page/Content/AxwayStartPage.htm).

2.  In the SEND command include at a minimum:

    -   The name of the final receiver, for example TARGET\_APPLICATION.
    -   The name of the flow, for example TEST\_RELAY.
    -   The file to be transferred, for example `report`.

    <!-- -->

        cftutil send part=target_application, idf=test_relay, fname=report

3.  Optionally you can configure target post-processing to automatically send a reply.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Tip  </strong></span>         </td>
         <td>You can use the script delivered with <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> in the <span>runtime/exec directory/BIN_re.cmd</span> as a basis for your ACK reply from the target application.         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When viewing the final transfer in the CG View Cycle Graph, you see the number of Transfer CFTs involved minus 1.         </td>
      </tr>
   </tbody>
</table>

<span id="Store2"></span>

## Store and forward with standalone <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>

The following sections describe various store and forward options when using standalone <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>s.

<span id="Intentional_Store_and_Forward"></span>

### Intentional store and forward

The following descriptions correspond with the
parameter setting example in the
figure below.

Configure the sender

Configure the following for the initial sender (Site A):

-   Define the final receiver CFTPART with both the OMINTIME and OMAXTIME parameters equal to zero.
-   Define the first relay (Site B).
-   In the final receiver partner definition, make a reference to the first relay with IPART=&lt;relay> .

Configure the relay

Configure the following for the store and forward (Site B):

-   Define both the initiator and the receiver CFTPART partner definitions.
-   Set COMMUT=YES (default).

Configure the receiver

Configure the following for the final receiver (Site C):

-   Define both the initiator and the relay CFTPART partner definitions.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>To enable acknowledgments from the receiver C to the sender A, in the receiver (C) configuration you must set the sender (A) CFTPART with OMINTIME and OMAXTIME parameters equal to zero, and define the relay (B) as the IPART.         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If the initial sender A is not
required to establish any direct physical connection with the final receiver
C, then the command CFTTCP ID=ID_C has no impact. Similarly, there is no need to set CFTTCP ID=ID_A
for the final receiver C.         </td>
      </tr>
   </tbody>
</table>

<span class="autonumber"></span>Intentional store and forward

<img src="/Images/TransferCFT/Intentional_store_and_forward.gif" width="769" height="631" />

<span id="Intentional_VAN_store_and_forward"></span>

### Intentional VAN store and forward

Use the same conditions as indicated in the [Intentional STORE and FORWARD](#Intentional_Store_and_Forward)
to establish the routing. For the store and forward site to be in VAN mode, you must additionally complete the store
and forward parameters as follows: <span class="code">CFTPART ID=ID\_A,COMMUT=SERVER,...</span>

The following descriptions correspond with the
parameter setting example in the
figure below.

Configure the sender

Configure the following for the initial sender (Site A):

-   Define the final receiver CFTPART with OMINTIME and OMAXTIME parameters equal to zero.
-   Define the first relay.
-   Make a reference to the first relay with IPART=&lt;relay> in the final receiver partner definition.

Configure the relay

Configure the following for the store and forward (Site B):

-   Define both the initiator and the receiver CFTPART partner definitions.
-   Set COMMUT=SERVER.
-   Define a procedure to execute and reference in the CFTPARM (in this example).
    -   In the store and forward example below, the procedure identified by <span class="code">myproc </span>
        includes the following command on completion of processing: <span class="code">CFTUTIL SEND **PART= &RPART**, **SPART= &SPART**, FNAME= &FNAME, IDF=
        &IDF</span>
    -   When the symbolic variables are replaced: <span class="code">CFTUTIL SEND **PART=ID\_C**,**SPART=ID\_A**,FNAME=frecv, IDF=test</span>

Configure the receiver

Configure the following for the final receiver (Site C):

-   Define both the initiator and the relay CFTPART partner definitions.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>In the example, the receiver (C) configuration defines the sender (Site A) CFTPART with OMINTIME and OMAXTIME parameters equal to zero, and defines the relay (Site B) as the IPART, which enables acknowledgments from the receiver C to the sender A.         </td>
      </tr>
   </tbody>
</table>

<span class="autonumber"></span>Intentional VAN store and forward

<img src="/Images/TransferCFT/Intentional_VAN_store_and_forward.gif" width="660" height="645" />

<span id="Forced_Store_and_Forward"></span>

### Forced store and forward

This feature, available only in the PeSIT protocol, is
used on an intermediate site to force the store and forward mode to another
site without knowing the final partner.

The following descriptions correspond with the
parameter setting example in the
figure below.

Configure the sender

-   Define the first relay (Intermediate Site 1).

Configure the first relay

Configure the following for the store and forward Intermediate Site 1:

-   Define the sender and the second relay (Site 2) = 2 CFTPARTs.
-   Set COMMUT=PART.

<!-- -->

-   In the CFTPART for the sender site, make a reference to the second relay using the IPART=&lt;Site 2>.

Configure the second relay

Configure the following for the store and forward Intermediate Site 2:

-   Define both the first relay (Intermediate Site 1) and the receiver partner definitions (CFTPARTs).
-   Set COMMUT=PART.
-   In the CFTPART for the first relay (Intermediate Site 1), make a reference to the final site.

Configure the final receiver

-   Define the CFTPART partner definition for the second relay (Intermediate Site 2).

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>To enable acknowledgments from the receiver to the sender, add the IPART for each CFTPART definition in each relay. For example:         </td>
      </tr>
   </tbody>
</table>

-   For the Intermediate Site 2 in the CFTPART ID=IDGWAY, set the IPART=IDDEP1, which refers to the Intermediate Site 1.
-   For the Intermediate Site 1 in the CFTPART ID=IDDEP, set the IPART=IDNAT1, which refers to the sender site.

Store and forward SEND command

In the SEND command you must specify the final network partner (the NSPART of the final partner) as well as the ID of the first intermediate partner.


    CFTUTIL SEND PART=NFINAL, IPART=IDNAT, ...

<span class="autonumber"></span>Forced store and forward

<img src="/Images/TransferCFT/Forced_Store_and_forward.gif" width="1183" height="1018" />

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The REPLY command may be sent when the end of transfer procedure is
executed (EXECRF). The acknowledgement message is then transferred in the same way, via
all the intermediate sites until it reaches the initial site (IPART =
…).         </td>
      </tr>
   </tbody>
</table>
