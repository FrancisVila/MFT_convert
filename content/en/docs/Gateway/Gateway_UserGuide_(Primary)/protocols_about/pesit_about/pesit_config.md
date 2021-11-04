{
    "title": "Configuring the PeSIT Hors SIT environment",
    "linkTitle": "Configuring PeSIT",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[About PeSIT Hors SIT configuration](#About_the_PeSIT_hors_SIT_configuration)

[Creating a Site](#Creating_a_Site)

[Creating an Application](#Creating_an_Application)

[Configuring Change Direction support](#Configuring_change_direction_support)

[Configuring negative acknowledgments](#Configuring_negative_acknowledgements)

[Canceling transfers on connection refusal](#cancel_transfer_on_conn_refusal)

<span id="About_the_PeSIT_hors_SIT_configuration"></span>

## About PeSIT Hors SIT configuration

Before submitting a file transfer, you must define the following Gateway objects if they do not already exist:

-   <span style="font-weight: bold;">Local Site</span>  
    On installation, you must create a Local Site corresponding to the alias name and protocol identifier of your Gateway system. This is the default Local Site for all protocols supplied by the product, including PeSIT. You can create a specific PeSIT Local Site if necessary
-   <span style="font-weight: bold;">Remote Site</span>  
    Define your partner Site and communication attributes in the Remote Site object. For the PeSIT service implementation, a Remote Site object must exist for each end user
-   <span style="font-weight: bold;">Application</span>  
    Define at least one Application

You can use either the <span class="code" style="font-weight: bold;">peladm</span> online command, as in the examples used here, or the GUI to create these objects.

<span id="Creating_a_Site"></span>

## Creating a Site

If you do not supply attributes explicitly, Gateway uses either default values from the operator interface or from Gateway internal defaults.

Some platforms may require values for optional attributes that differ from the defaults. Refer to your platform-specific documentation for more information.

If you do not specify a group for the Remote Site that you create, Gateway assigns the group name GDEFAULT.

#### Example 1: Creating a Local Site **locpsit**

peladm create\_loc\_site  -alias locpsit

   -pi locpsit

   -comments "PHSD Local Site"

#### Example 2: Creating a Local Site acting in Responder mode only

peladm create\_loc\_site  -alias locpsit1

   -pi locpsit1

   -no\_i\_s

   -no\_r\_r

#### Example 3: Creating a Remote Site using TCP/IP and the following attributes

-   PeSIT Hors SIT E
-   Remote IP address: 193.56.234.20
-   Port number: 22222
-   Maximum buffer size: 2048 bytes
-   Synchronization acknowledgment window: 8 (KB)
-   Maximum number of simultaneous server connections: 10
-   Responder/Sender mode: disabled

peladm create\_site  -alias tcpphse

   -protocol PHSE

   -comments "Remote Site: PESIT version E, TCP"

   -comm\_type TCP

   -dest\_address 193.56.234.20/22222

   -data\_size\_max 2048

   -resp\_conn\_max 10

   -no\_r\_s

<span id="Creating_an_Application"></span>

## Creating an Application

Gateway completes any attributes that you do not define with default values from either the operator interface, or from internal default attributes.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">If Application does not exist in this scenario         </th>
<th class="HeadD-Column1-Header1">Gateway uses this default         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>For file reception in Responder mode</p>         </td>
         <td><p><span style="font-style: italic;">DEFAULT_X</span></p>
<p>where X can take the values:</p>
<ul>
<li>A for ASCII transfers</li>
<li>E for EBCDIC transfers</li>
<li>B for binary transfers</li>
</ul>         </td>
      </tr>
      <tr>
         <td>No <span style="font-style: italic;">DEFAULT_X</span> Applications are defined         </td>
         <td><p>Application <span style="font-style: italic;">DEFAULT_X</span>(if found) is used</p>
<p><span style="font-weight: bold;">Note:</span> Applications with these names must be defined in both partner Sites.</p>         </td>
      </tr>
   </tbody>
</table>

#### Example 1: Defining the default Applications named DEFAULT\_A and DEFAULT\_B

peladm create\_appli  -n DEFAULT\_A

   -text\_file  Y

peladm create\_appli  -n DEFAULT\_B

#### Example 2: Creating an Application to send a fixed-length file

This example creates an Application named **FIX255** to send a file that contains **255**-byte fixed-length records.

peladm create\_appli  -n fix255

   -rec\_fmt F

   -rec\_len 255

   -x\_rec\_fmt F

   -x\_rec\_len 255

#### Example 3: Creating an Application to send a variable-length file

This example creates an Application named **VAR255** to send a file that contains variable-length records with a maximum length of 255.

peladm create\_appli  -n fix255

   -rec\_fmt V

   -rec\_len 255

   -x\_rec\_fmt V

   -x\_rec\_len 255

<span id="Configuring_change_direction_support"></span>

## Configuring Change Direction support

PeSIT Hors SIT Change Direction (CD) support is only available in PeSIT Hors SIT E.

The PeSIT Hors SIT protocol enables a client application (the connection Initiator) to call a server (the connection Responder), and then to send files to, or to ask to receive files from the server. The server application waits for client connection requests to receive files from the client, or to transmit files to the client upon a selection request.

The official protocol specification does not allow a server application to send files or a message, on its own initiative, to the client application. This is normally not a problem since a file transfer monitor can initiate as well as receive connection requests, thus assuming the roles of client and server alternatively during different sessions.

However, under more restrictive circumstances, such as a file transfer monitor situated within a DMZ (Demilitarized Zone), it may be forced to disable the client role, which means it is no longer allowed to initiate a connection request. In such cases, there is no way to send a PeSIT Hors SIT message (either an application or acknowledgment message) from the server to the client.

<span style="font-weight: bold;">Note:</span> PeSIT Hors SIT Change Direction Support is a proprietary extension to the official PeSIT Hors SIT E protocol specification.

### PeSIT Hors SIT Change Direction Site parameters

To implement PeSIT Hors SIT Change Direction support, four specific parameters are available when defining a PeSIT Hors SIT E Remote Site.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadE-Column1-Header1">Value         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Change Direction Option</p>         </td>
         <td><p>YES | NO</p>         </td>
         <td><p>Indicates whether the Remote Site supports the Change Direction extension or not. If you do not set this option, the following parameters are ignored.</p>         </td>
      </tr>
      <tr>
         <td><p>Polling Activation Mode</p>         </td>
         <td><p>YES | NO</p>         </td>
         <td>Indicates whether or not the Remote Site in question is polled when you start Gateway. This parameter also enables the CD connection to be dynamically activated or deactivated (see <span class="code" style="font-weight: bold;">pelctl</span> command below).         </td>
      </tr>
      <tr>
         <td><p>Polling Interval</p>         </td>
         <td><p>mm (minutes)</p>         </td>
         <td><p>Defines the time to wait before starting the next calling cycle.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum Connections</p>         </td>
         <td><p>Nn (integer)</p>         </td>
         <td><p>Defines the upper limit of concurrent active connections in Change Direction mode.</p>
<p><span style="font-weight: bold;">Note:</span> The CD connections are counted separately from the normal Initiator and Responder connections established with this Site.</p>         </td>
      </tr>
   </tbody>
</table>

#### Example

Client Side Monitor               Server Side Monitor (within DMZ)

    remote\_server\_pesit\_hs\_site         remote\_client\_pesit\_hs\_site

          CD option   : YES             CD option         : YES

          CD mode     : YES             CD mode           : NO

          CD interval : 60              CD interval       : 0

          CD max conn : 10              CD max conn       : 0

### Online commands for Site parameters

Use the online commands:

-   <span class="code" style="font-weight: bold;">peladm create\_site</span> and <span class="code" style="font-weight: bold;">peladm update\_site</span> to define the Remote Site features
-   <span class="code" style="font-weight: bold;">pelctl start\_site</span> and <span class="code" style="font-weight: bold;">pelctl stop\_site</span> to enable the CD connection to be dynamically activated or deactivated.

The specific parameters required to configure this feature are:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Command         </th>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Comment         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>peladm create_site</p>         </td>
         <td><p>-poll_option (-poll) Y | N</p>
<p>-poll_mode (-pm) Y | N</p>
<p>-poll_interval (-pollint) mm</p>
<p>-poll_conn_max (-pollmax) nn</p>         </td>
         <td><p>Define the Remote Site features as described here.</p>
<p>The default values are NO and zero. Other parameters are unchanged.</p>         </td>
      </tr>
      <tr>
         <td><p>peladm update_site</p>         </td>
      </tr>
      <tr>
         <td><p>pelctl start_site</p>         </td>
         <td><p>-poll_mode (-pm)</p>         </td>
         <td><p>The value set by these two commands overrides that defined in the Site object. However, this value is transient and valid only for the current Gateway session. At the next Gateway startup session, this field reverts to the value specified in the Site definition.</p>         </td>
      </tr>
      <tr>
         <td><p>pelctl stop_site</p>         </td>
      </tr>
   </tbody>
</table>

### How it works

When you define a Remote Site to support the CD option, with <span class="code">poll\_mode=Y</span>:

-   The client application automatically initiates a PeSIT Hors SIT connection with a modified version (with PI 6 bit 7 set to 1) to indicate that CD support is desired
-   The server application can either accept or refuse the connection

Once the protocol connection is established and the two partners are successfully authenticated, the client application sends a SELECT request with a modified PI 14 (set to 0xFF) to indicate that a CD is requested.

Recognizing the modified SELECT request, the server application answers with an ACK.SELECT with a modified PI 33 (set to 0xFF) to acknowledge the CD request.

Thereafter, the client application switches to Responder mode and the server application to Initiator mode.

The server is then free to send files or messages as defined by the formal protocol specification.

If no files or messages are available, the server application can release the connection and the client application retries on the next cycle as defined by the scheduling parameters.

If the client application, after exchanging SELECT/ACK.SELECT, receives a file or message transmission indication, it either:

-   immediately schedules another connection request to see if there are more files or messages to process (on condition that the maximum number of concurrent connections is not reached)
-   launches the next cycle when one of the current connections is terminated

<span id="Configuring_negative_acknowledgements"></span>

## Configuring negative acknowledgments

Negative acknowledgment (PeSIT Hors SIT Negative EERP Support) is only available in PeSIT Hors SIT E.

The PeSIT Hors SIT E protocol supports an EERP (end-to-end) acknowledgment. In this positive acknowledgment, the final destination of a file transfer can send a message to the transfer originator to acknowledge reception of the file. However, the formal protocol specification does not specify how to send a negative acknowledgment to signal whether errors occurred. For example, errors detected or generated by a user application or by the intermediate Sites during Store-and-Forward processing.

<span style="font-weight: bold;">Note:</span> PeSIT Hors SIT Negative EERP Support is a proprietary extension to the official PeSIT Hors SIT E protocol specification.

### PeSIT Hors SIT E Site Negative EERP parameters

To implement PeSIT Hors SIT negative EERP support, a new parameter is included in the definition of a PeSIT Hors SIT E Remote Site.

<span style="font-weight: bold;">Negative acknowledgment option</span> <span class="code">(-nack\_option)</span>: YES | NO

The NACK (Negative acknowledgment) option indicates whether the Remote Site supports the negative EERP extension or not. If this option is not set to *Yes*, all negative EERP requests are denied.

### Online commands for Site parameters

Use the online commands:

-   <span class="code" style="font-weight: bold;">peladm create\_site</span> and <span class="code" style="font-weight: bold;">peladm update\_site</span> to define the Remote Site features
-   <span class="code" style="font-weight: bold;">peltrans</span> to specify negative EERP

The specific parameters required to configure this feature are:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Command         </th>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Default values         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>peladm create_site</p>         </td>
         <td><p>-nack_option (-nao) Y | N</p>         </td>
         <td><p>N</p>         </td>
      </tr>
      <tr>
         <td><p>peladm update_site</p>         </td>
      </tr>
      <tr>
         <td><p>peltrans</p>         </td>
         <td><p>-nack_by_user (-nack) Y | N</p>         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

### How it works

When you define a Remote Site to support negative EERP:

-   The client application initiates a PeSIT HS connection with a modified version (with PI 6 bit 8 set to 1) to indicate that negative EERP support is requested
-   The server application can either accept or refuse the connection
-   Once the protocol connection is established and the two partners are successfully authenticated, the client application can send a MESSAGE request with a modified PI 14 to indicate that this is a negative EERP

<span style="font-weight: bold;">Note:</span> PI 14 set to 0xFE indicates a user-initiated negative EERP. PI 14 set to 0xFF indicates a Gateway-initiated negative EERP.

The message contents are provided either by a user application or generated automatically by Gateway, as in the case of a normal EERP.

Recognizing the modified PI 14, the server application updates the file transfer status accordingly.

<span id="cancel_transfer_on_conn_refusal"></span>

## Canceling transfers on connection refusal

If required, you can cancel transfers to a Site that is reachable but refuses connections. To do this, you modify the <span class="code">cancel\_transfer\_on\_connection\_refusal</span> advanced parameter in the Gateway configuration menu.

Refer to [Configuration: Gateway parameters - Advanced parameters and Trace levels](../../../configuration_start_here/config_gateway_paras#Advanced_parameters).

The value of this parameter only affects transfers made using the PeSIT protocol.

 

Related topics

[Working with Local Sites](../../../managing_partners_start_here/sites_start_here/managing_local_sites)

[Working with Local Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli)

[Working with Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites)

[Working with Remote Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli)

[Working with Applications](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_(gui))

[Working with Applications (command line)](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_cli)

[Executing a basic PeSIT transfer](../../../transfer_examples/transfer_example_pesit)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
