{
    "title": "My first file transfer (CL)",
    "linkTitle": "First file transfer with standalone Transfer CFT",
    "weight": "100"
}After installing your Transfer CFT, you can use the delivered configuration samples and default values to quickly and easily perform your first transfer.

For more information on starting your <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, and basic operational commands, see the section [Start, stop, and <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> administrative scripts.](../../admin_intro/start_stop_cft)

This topic describes how to:

-   [Perform a file transfer using the sample configuration](#Perform)
-   [Perform a standard mode transfer](#Perform2)
-   [Use the explicit mode to get a file](#Use)
-   [Receive multiple files from a partner](#Receive)
-   [Use the implicit transfer mode](#Use2)
-   [Send using open mode](#Send)
-   [Receive using open mode](#Receive2)
-   [Perform broadcast and collect operations](#Perform3)

<span id="Perform"></span>

## Perform a file transfer using the sample configuration

The sample file features two default partners, NEWYORK and PARIS. Each of these partners is pre-configured to communicate using the [PeSIT](../../protocols_start_here/about_pesit) protocol. Additionally, both of these partners listen on the localhost interface. You can begin with a simple transfer, and then check the catalog for transfer details.

To send a file from PARIS to NEWYORK, run the following command:


    CFTUTIL send part=NEWYORK, idf=txt

To check in the Transfer CFT catalog to confirm that the transfer completed successfully, enter:


    CFTUTIL listcat

You should see that the default file was sent from NEWYORK to PARIS. There are two entries are displayed, this is due to the fact that you performed a loop transfer using the localhost interface.



    Partner  DTSAPP File     Transfer         Records       Diags        Appli.   Appstate.
                    Id.      Id.       Transmit     Total   CFT Protocol Id.
    -------- ------ -------- -------- ---------- ---------- --- -------- -------- ---------
    NEWYORK  SFX XX TXT      J2220582        112        112   0 CP NONE
    PARIS    RFX XX TXT      J2220582        112        112   0 CP NONE

To display exhaustive transfer details, enter the command:


    CFTUTIL listcat content=debug

The purpose of the My first file transfer section is to help you feel comfortable with basic <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> file transfer commands. Once you understand core file transfer concepts, you can delve into the rich array of parameters that allow you to customize your application integrations and data flows. Additional commands and options are available to help you define the monitoring granularity  for your executed transfers.

## What's next?

In the following sections, we'll take a look at additional <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> transfer modes, as well as some useful configuration parameters. With Transfer CFT, the transfer initiator can be either the sender of the file or the receiver, as indicated in the examples below. Additionally, in these examples we will use the convention that the requester is the client, so the transfer description may read <span class="bold_in_para">Requester/Sender</span> if the client is supplying the file.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>For more information on a command and a list of available parameters, enter <span class="code">CFTUTIL help cmd=&lt;name of command&gt;</span>.         </td>
      </tr>
   </tbody>
</table>

<span id="Perform2"></span>

### Perform a standard mode transfer

Let's start by performing the same type of transfer as in the sample configuration above, but without using the samples. First, you need to create two partners, and then exchange a file.

![In this example, the Requester Paris site sends file to the Server New York site](/Images/TransferCFT/2013_g_TransferCFT_Standard_mode.png)

 

<table>
   <th>
      <tr>
<th>Requester/Sender         </th>
<th>Server/Receiver         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Configuration</strong></p>
<ol>
<li>Create a partner.</li>
<li>Create an IDF.</li>
</ol>
<p><strong>Runtime</strong></p>
<ol start="3">
<li>Run the transfer.</li>
</ol>
<ol start="4">
<li>Check the catalog.</li>
</ol>         </td>
         <td><p><strong>Configuration</strong></p>
<ol>
<li>Create a partner.</li>
<li>Create an IDF.</li>
</ol>
<p><strong>Runtime</strong></p>
<ol start="3">
<li>Retrieve the sent file.</li>
<li>Check the catalog.</li>
</ol>         </td>
      </tr>
   </tbody>
</table>

View an example



    /*REQUESTER/SENDER*/

    CFTPART 
         ID =     NEWYORK,      
    PROT =     PESITANY, 
         SAP =     1761, /*remote listening port for NewYork*/
    NRPART =     NEWYORK, 
         NSPART =     PARIS,
     
    CFTTCP 
    ID=NEWYORK,
    HOST = @<NEWYORK address>
     
    CFTSEND ID=INVOICE,...
     
    SEND PART=NEWYORK, IDF=INVOICE
     
    LISTCAT

 



    /*SERVER/RECEIVER*/

    CFTPART     
         ID =     PARIS,      
    PROT =     PESITANY, 
         SAP =         1761, /*remote listening port for Paris*/
    NRPART =     PARIS, 
         NSPART =     NEWYORK,
     
    CFTTCP 
    ID=PARIS,
    HOST = @<PARIS address>
     
    CFTRECV ID=INVOICE, FNAME=MYFILE
     
    LISTCAT

<span id="Use"></span>

### Use the explicit mode to get a file

In explicit mode, an application makes a specific file available for a defined partner. Then when that particular remote partner is ready, it can retrieve the specified file, which only needed to be made available once.

<img src="/Images/TransferCFT/2013_g_TransferCFT_Explicit_mode.png" class="maxWidth" alt="In this example, the Sender site Phoenix has a file available for the Requester Paris site" />

 

<table>
   <th>
      <tr>
<th>Server/Sender         </th>
<th>Requester/Receiver         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Configuration</p>
<ol>
<li>Create a partner.</li>
<li>Create an IDF.</li>
</ol>
<p> </p>
<p> </p>
<p>Runtime</p>
<ol start="3">
<li><p>Make your file available.</p>
<p>The send command is set with the ‘state=HOLD’ parameter. The HOLD attribute puts the file in the Transfer CFT catalog, and indicates that it is available for the partner.</p></li>
<li>Check the catalog.</li>
</ol>         </td>
         <td><p>Configuration</p>
<ol>
<li>Create a partner.</li>
<li>Create an IDF.</li>
</ol>
<p> </p>
<p> </p>
<p>Runtime</p>
<ol start="3">
<li>Receive the available file.</li>
</ol>
<ol start="4">
<li>Check the catalog.</li>
</ol>         </td>
      </tr>
   </tbody>
</table>

View an example



    /*SERVER/SENDER*/

    CFTPART     
         ID =     PARIS,      
    PROT =     PESITANY, 
         SAP =     1761, /*remote listening port for Phoenix*/
    NSPART =     PHOENIX, 
         NRPART =     PARIS,
    CFTTCP 
    ID=PARIS, 
    HOST = @<Paris address>
     
    CFTSEND ID=INVOICE, IMPL=NO,....
     
    SEND PART=PARIS, IDF=INVOICE, STATE=HOLD 
     
    LISTCAT /*show transfers in hold state*/



    /*REQUESTER/RECEIVER*/

    CFTPART     
         ID =     PHOENIX,      
    PROT =     PESITANY, 
         SAP =     1761, /* remote listening port for Paris */
    NSPART =     PARIS, 
         NRPART =     PHOENIX,
    CFTTCP 
    ID=PHOENIX, 
    HOST = @<Phoenix address> 
     
    CFTRECV ID=INVOICE,....
     
    RECV PART=PHOENIX, IDF=INVOICE, FNAME=MY_FILE
     
    LISTCAT

<span id="Receive"></span>

### Receive multiple files from a partner

This transfer mode is the same as the previously described explicit mode but provides multiple files for a defined partner. So an application might create several files and set them to an available state, and the remote partner can then retrieve these when ready, for example at a scheduled time.

![In this example, the Sender Phoenix site has multiple files availalbe for the Requester site](/Images/TransferCFT/2013_g_TransferCFT_Multiple_receive.png)

 

<table>
   <th>
      <tr>
<th>Server/Sender         </th>
<th><p>Requester/Receiver</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Configuration</p>
<ol>
<li>Create a partner.</li>
<li>Create an IDF.</li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>Make a file available SEND part=PARIS, idf=INVOICE, state=HOLD.</li>
<li>Repeat with another file.</li>
<li>Repeat again with a third file. This ‘HOLD’ attribute puts the files in the Transfer CFT catalog and makes them available for the partner.</li>
</ol>
<ol start="6">
<li>Check the catalog for 1 entry per transfer. A generic entry is set.</li>
</ol>         </td>
         <td><p>Configuration</p>
<ol>
<li>Create a partner.</li>
<li>Create an IDF.</li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>Receive all of the available files:<br />
RECV part=PHOENIX, idf=INVOICE, file=ALL.</li>
</ol>
<ol start="4">
<li>Check the catalog for 1 entry per transfer. A generic entry is set.</li>
</ol>         </td>
      </tr>
   </tbody>
</table>

View an example



    /*SERVER/SENDER*/

    CFTPART     
         ID =     PARIS,      
    PROT =     PESITANY, 
         SAP =     1761, /*remote listening port for Phoenix*/
    NSPART =     PHOENIX, 
         NRPART =     PARIS,
    CFTTCP 
    ID=PARIS, 
    HOST = @<Paris address>
     
    CFTSEND ID=INVOICE, IMPL=NO,....
     
    SEND PART=PARIS, IDF=INVOICE, STATE=HOLD, FNAME=FILE_1
    SEND PART=PARIS, IDF=INVOICE, STATE=HOLD, FNAME=FILE_2
    SEND PART=PARIS, IDF=INVOICE, STATE=HOLD, FNAME=FILE_n
     
    LISTCAT /*would show transfer in hold state*/



    /*REQUESTER/RECEIVER*/

    CFTPART     
         ID =     PHOENIX,      
    PROT =     PESITANY, 
         SAP =     1761, /* remote listening port for Paris */
    NSPART =     PARIS, 
         NRPART =     PHOENIX,
    CFTTCP 
    ID=PHOENIX, 
    HOST = @<Phoenix address> 
     
    CFTRECV ID=INVOICE, FNAME=@IDTU.RCV,...
     
    RECV PART=PHOENIX, IDF=INVOICE, FILE=ALL
     
    LISTCAT

<span id="Use2"></span>

### Use the implicit transfer mode

The implicit transfer mode is often used to make a file whose content is frequently changing available to partners. The file is always available and partners can retrieve it as many time as necessary.

<img src="/Images/TransferCFT/2013_g_TransferCFT_Implicit_mode.png" class="maxWidth" alt="In this example, the Sender Phoenix site has a file whose contents may be frequently updated availbe" />

 

<table>
   <th>
      <tr>
<th>Server/Sender         </th>
<th>Requester/Receiver         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Conf</p>
<ol>
<li>Create a partner.</li>
<li>Create an IDF where impl=yes.</li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>The CFTSEND is set with ‘impl=yes’.</li>
<li>Check the catalog.</li>
</ol>         </td>
         <td><p>Conf</p>
<ol>
<li>Create a partner.</li>
<li>Create an IDF.</li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>Receive the file.</li>
</ol>
<ol start="4">
<li>Check the catalog.</li>
</ol>         </td>
      </tr>
   </tbody>
</table>

View an example



    /*PHOENIX*/

    CFTPART     
         ID =     PARIS,      
    PROT =     PESITANY, 
         SAP =     1761, /*remote listening port for Phoenix*/
    NSPART =     PHOENIX, 
         NRPART =     PARIS,
    CFTTCP 
    ID=PARIS, 
    HOST = @<Paris address>
     
    CFTSEND ID=ORDER, IMPL=YES, FNAME=FILE_TO_SEND....
     
     
    LISTCAT /*would show transfer in hold state*/

 



    /*PARIS*/

    CFTPART     
         ID =     PHOENIX,      
    PROT =     PESITANY, 
         SAP =     1761, /* remote listening port for Paris */
    NSPART =     PARIS, 
         NRPART =     PHOENIX,
    CFTTCP 
    ID=PHOENIX, 
    HOST = @<Phoenix address> 
     
    CFTRECV ID=ORDER,....
     
    RECV PART=PHOENIX, IDF=ORDER, FNAME=MY_FILE
     
    LISTCAT

<span id="Send"></span>

### Send using open mode

This mode is similar to the FTP put command. It allows you to define the file name in the remote partner. The receiver must accept the open mode. Then, using a simple SEND command allows you to send a file to a partner in a dedicated directory with a dedicated file name.

![In this example, the Sender New York site is sending a file to a partner that receives in open mode](/Images/TransferCFT/2013_g_TransferCFT_Open_mode_send.png)

 

<table>
   <th>
      <tr>
<th>Requester/Sender         </th>
<th>Server/Receiver         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Conf</p>
<ol>
<li>Create a partner.</li>
<li>Create a CFTSEND with fname=&lt;FILE_TO_SEND&gt;, nfname=cft/filpub/fic.txt …</li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>Run the transfer.</li>
</ol>
<ol start="4">
<li>Check the catalog.</li>
</ol>         </td>
         <td><p>Conf</p>
<ol>
<li>Create a partner.</li>
<li><p>Create an CFTRECV fname=&amp;nfname…</p>
<p>The syntax ‘fname=&amp;nfname’ means that the receiver allows the open mode.</p></li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>The file has been stored in the path defined by the client/sender, in this example: cft/filpub/fic.txt.</li>
<li>Check the catalog.</li>
</ol>         </td>
      </tr>
   </tbody>
</table>

View an example



    /*REQUESTER/SENDER*/ 

    CFTPART 
         ID =     NEWYORK,      
    PROT =     PESITANY, 
         SAP =     1761, /*remote listening port for NewYork*/
    NRPART =     NEWYORK, 
         NSPART =     PARIS,
     
    CFTTCP 
    ID=NEWYORK,
    HOST = @<NEWYORK address>
     
    CFTSEND ID=INVOICE,FNAME=FILE_TO_SEND, NFNAME=<remote_location_pathname>
     
    SEND PART=NEWYORK, IDF=INVOICE
     
    LISTCAT

 



    /*RECEIVER/SERVER*/

     
    CFTPART     
         ID =     PARIS,      
    PROT =     PESITANY, 
         SAP =         1761, /*remote listening port for Paris*/
    NRPART =     PARIS, 
         NSPART =     NEWYORK,
     
    CFTTCP 
    ID=PARIS,
    HOST = @<PARIS address>
     
    CFTRECV ID=INVOICE, FNAME=MYFILE,FNAME=&NFNAME
     
    LISTCAT

<span id="Receive2"></span>

### Receive using open mode

This mode is similar to FTP get command. It allows the receiver to get a file from the sender in a dedicated location.  The receiver must accept the open mode. Then, a simple RECV command allows to get a file from a partner from a dedicated directory with a dedicated file name.

![In this example, the Receiver site gets a file from the Sender](/Images/TransferCFT/2013_g_TransferCFT_Open_mode_receive.png)

 

<table>
   <th>
      <tr>
<th><p>Requester/Receiver</p>         </th>
<th>Server/Sender         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Configuration</p>
<ol>
<li>Create a partner.</li>
<li>Create an CFTRECV that defines the fname.</li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>Request the file stored on the remote server. Run the command: CFTUTIL RECV… nfname=&lt;remote_requested_file&gt;.</li>
</ol>
<ol start="4">
<li>The file retrieved is stored in the fname location.</li>
<li>Check the catalog.</li>
</ol>         </td>
         <td><p>Configuration</p>
<ol>
<li>Create a partner.</li>
<li><p>Create an CFTSEND where impl=yes, fname=&amp;nfname.</p>
<p>The syntax ‘fname=&amp;nfname’ means that the server/sender allows the open mode.</p></li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>The file stored locally in &lt;remote_requested_file&gt; is sent to the client.</li>
</ol>
<ol start="4">
<li>Verify the catalog</li>
</ol>         </td>
      </tr>
   </tbody>
</table>

View an example



    /*REQUESTER/RECEIVER*/ 
    CFTPART 
         ID =     NEWYORK,      
    PROT =     PESITANY, 
         SAP =     1761, /*remote listening port for NewYork*/
    NRPART =     NEWYORK, 
         NSPART =     PARIS,
     
    CFTTCP 
    ID=NEWYORK,
    HOST = @<NEWYORK address>
     
    CFTRECV ID=INVOICE, FNAME=<local_download_location>
     
    RECV PART=NEWYORK, IDF=INVOICE, NFNAME=<remote_requested_file>
     
    LISTCAT

 



    /*SERVER/SENDER*/

    CFTPART     
         ID =     PARIS,      
    PROT =     PESITANY, 
         SAP =         1761, /*remote listening port for Paris*/
    NRPART =     PARIS, 
         NSPART =     NEWYORK,
     
    CFTTCP 
    ID=PARIS,
    HOST = @<PARIS address>
     
    CFTSEND ID=INVOICE, IMP=YES,FNAME=&NFNAME
     
    LISTCAT

<span id="Perform3"></span>

### Perform broadcast and collect operations

Broadcast and collect modes allow you to send files to multiple partners and receiving files from multiple partners using a single command request for each.

#### Broadcasting

You can use broadcasting to send a file to an entire group of partners in one command, avoiding the task of sending the selected file individually to each of the partners in a flow.

The name of the broadcast list is itself a virtual partner, which contains a list of partners in your flow. This list of partners can be explicit, or it can reference a file that contains the list of partners.

Additionally, you can define what occurs if a partner is unknown, how the scripts are applied to the broadcast list, and so on.

[More information](../../concepts/transfer_command_overview/broadcast_collect)...

![In this example, the Sender Paris site sends a file to an entire group of partners in one command](/Images/TransferCFT/2013_g_TransferCFT_Broadcast1.png)

 

<table>
   <th>
      <tr>
<th>Requester/Sender         </th>
<th>Server/Receiver – PHOENIX         </th>
<th>Server/Receiver – NEWYORK         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Configuration</p>
<ol>
<li>Create a first partner NEWYORK.</li>
<li>Create a second partner PHOENIX.</li>
<li>Create a broadcast list that contains both part1 and part2.</li>
<li>Create a CFTSEND.</li>
</ol>
<p>Runtime</p>
<ol start="5">
<li>Using one command, send a file to the broadcast list.</li>
<li>The file is sent to both partners at the same time.</li>
</ol>
<ol start="7">
<li>Check the catalog. You should have 3 entries in the catalog, one generic entry and one entry per partner.</li>
</ol>         </td>
         <td><p>Configuration</p>
<ol>
<li>Create a first partner.</li>
<li>Create an CFTRECV.</li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>The first partner receives the file.</li>
</ol>
<ol start="4">
<li>Check the catalog, there should be get one entry for this partner.</li>
</ol>         </td>
         <td><p>Configuration</p>
<ol>
<li>Create a second partner.</li>
<li>Create an CFTRECV.</li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>The second partner receives the file.</li>
</ol>
<ol start="4">
<li>Check the catalog, there should be get one entry for this partner.</li>
</ol>
<p> </p>
<p> </p>         </td>
      </tr>
   </tbody>
</table>

View an example



    /*SENDER*/ 
    CFTPART     
         ID =     PHOENIX,      
    PROT =     PESITANY, 
         SAP =     1761, /*remote listening port for Phoenix*/
    NSPART =     PARIS, 
         NRPART =     PHOENIX,
    CFTTCP 
    ID=PHOENIX, 
    HOST = @<PHOENIX address>
     
    CFTPART     
         ID =     NEWYORK,      
    PROT =     PESITANY, 
         SAP =     1761, /*remote listening port for New York*/
    NSPART =     PARIS, 
         NRPART =     NEWYORK,
    CFTTCP 
    ID=NEWYORK, 
    HOST = @<NEWYORK address>
     
    CFTDEST ID=DEST01, PART=NEWYORK, PHOENIX
     
    CFTSEND ID=ORDER
     
    SEND PART=DEST01, IDF=ORDER
     
    LISTCAT 

 



    /*RECEIVER 1*/

    CFTPART     
         ID =     PARIS,      
    PROT =     PESITANY, 
         SAP =     1761, /* remote listening port for Paris */
    NSPART =     PHOENIX, 
         NRPART =     PARIS,
    CFTTCP 
    ID=PARIS, 
    HOST = @<PARIS address> 
     
    CFTRECV ID=ORDER,....
     
    LISTCAT

 



    /*RECEIVER 2*/

    CFTPART     
         ID =     PARIS, 
    PROT =     PESITANY, 
         SAP =     1761, /* remote listening port for Paris */
    NSPART =     NEWYORK, 
         NRPART =     PARIS,
    CFTTCP 
    ID=PARIS, 
    HOST = @<PARIS address> 
     
    CFTRECV ID=ORDER,....
     
    LISTCAT

#### Collecting

Collecting files is the inverse of using a broadcast list. In the collect transfer mode you can receive a dedicated file from multiple partners (P*n*). This allows the receiver, or flow initiator, to receive a file from all defined partners using a single request command.

More information...

![In this example, the Receiver Paris site collects or receives a dedicated file from multiple partners](/Images/TransferCFT/2013_g_TransferCFT_Collect1.png)

<table>
   <th>
      <tr>
<th>Client/Receiver         </th>
<th><p>Server/Sender</p>
<p>PHOENIX</p>         </th>
<th><p>Server/Sender</p>
<p>NEW YORK</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Configuration</p>
<ol>
<li>Create a first partner.</li>
<li>Create a second partner.</li>
<li>Create a collect list containing both NEW YORK and PHOENIX.</li>
<li>Create a CFTRECV.</li>
</ol>
<p>Runtime</p>
<ol start="5">
<li>Using a single command, receive a file from both (all) partners using the defined collect list.</li>
</ol>
<ol start="6">
<li>Both files are received from both partners at the same time</li>
</ol>
<ol start="7">
<li>Check the catalog. You should have 3 entries in the catalog, one generic entry and one entry per partner.</li>
</ol>         </td>
         <td><p>Configuration</p>
<ol>
<li>Create this partner.</li>
<li>Create an CFTSEND.</li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>This partner makes a file available for the client SEND state=HOLD.</li>
</ol>
<ol start="4">
<li>The first partner sends the file.</li>
</ol>
<ol start="5">
<li>Check the catalog, there should be one entry.</li>
</ol>         </td>
         <td><p>Configuration</p>
<ol>
<li>Create a this partner.</li>
<li>Create an CFTSEND.</li>
</ol>
<p>Runtime</p>
<ol start="3">
<li>This partner makes a file available for the client SEND state=HOLD.</li>
</ol>
<ol start="4">
<li>The second partner sends the file.</li>
<li>Check the catalog, there should be one entry.</li>
</ol>         </td>
      </tr>
   </tbody>
</table>

View an example



    /*RECEIVER*/ 

    CFTPART     
         ID =     PHOENIX,      
    PROT =     PESITANY, 
         SAP =     1761, /*remote listening port for Phoenix*/
    NSPART =     PARIS, 
         NRPART =     PHOENIX,
    CFTTCP 
    ID=PHOENIX, 
    HOST = @<PHOENIX address>
     
    CFTPART     
         ID =     NEWYORK,      
    PROT =     PESITANY, 
         SAP =     1761, /*remote listening port for New York*/
    NSPART =     PARIS, 
         NRPART =     NEWYORK,
    CFTTCP 
    ID=NEWYORK, 
    HOST = @<NEWYORK address>
     
    CFTDEST ID=DEST01, PART=NEWYORK, PHOENIX
     
    CFTRECV ID=ORDER
     
    RECV PART=DEST01, IDF=ORDER, FNAME=<...>&part
     
    LISTCAT 

 



    /*SENDER 1*/

    CFTPART     
         ID =     PARIS,      
    PROT =     PESITANY, 
         SAP =     1761, /* remote listening port for Paris */
    NSPART =     PHOENIX, 
         NRPART =     PARIS,
    CFTTCP 
    ID=PARIS, 
    HOST = @<PARIS address> 
     
    CFTSEND ID=ORDER,...
     
    SEND IDF=ORDER, STATE=HOLD
     
    LISTCAT

 



    /*SENDER 2*/

    CFTPART     
         ID =     PARIS, 
    PROT =     PESITANY, 
         SAP =     1761, /* remote listening port for Paris */
    NSPART =     NEWYORK, 
         NRPART =     PARIS,
    CFTTCP 
    ID=PARIS, 
    HOST = @<PARIS address> 
     
    CFTSEND ID=ORDER,...
     
    SEND IDF=ORDER, STATE=HOLD
     
    LISTCAT

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>In these examples we created partners using the default MODE value, which is REPLACE. You can also use the MODE=CREATE, to create a new <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner.         </td>
      </tr>
   </tbody>
</table>

#### Additional information

Once you understand the basic modes and concepts described in this topic, you can then add processing, symbolic variables, scripts and more to your transfers using other <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> options and features. See the dedicated sections in this document for details on customizing your transfer flows. A good place to start is [Transfer Concepts](../../concepts/transfer_command_overview), which presents high-level transfer processing concepts, transfer mode details, and procedural topics.