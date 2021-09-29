{
    "title": "Synchronous communication services in C",
    "linkTitle": "Synchronous communication services in C",
    "weight": "370"
}# <span id="Synchronous_communication_services"></span>Synchronous communication services

This topic describes Transfer CFT synchronous communication services.

## Description of functions

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Function</p></th>
<th><p>Use</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>COM</p></td>
<td><p>Set the communication medium</p></td>
</tr>
<tr class="even">
<td><p>GETXINFO</p></td>
<td><p>Retrieve information concerning the last transfer made
from a synchronous request after a request of the following types: SEND,
RECV, HALT, KEEP, START, RESUME, DELETE, END, SUBMIT, SWITCH, PURGE.</p>
<p>The information is stored in a cftApiInf-type structure:</p>
<ul>
<li>Transfer
state</li>
<li>Diagnostic</li>
<li>Diagnostic
protocol</li>
<li>Value
of the PART field of CFTPARM</li>
<li>Transfer
identifier (IDT)</li>
<li>Local
transfer identifier (IDTU)</li>
<li>Transfer
type (single, cyclical, diffusion list, collection, file group)</li>
<li>Public
reference of the transfer (only for a single transfer in Send)</li>
</ul>
<p>The GETXINFO action returns an error if the communication
medium is not synchronous.</p>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The public
reference of the transfer is a character string of variable length. In
the PESIT protocol, it contains 'pi13.pi3.pi4.pi11.pi12.pi61.pi62'.</td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>

## <span id="Call Syntax"></span>Call syntax

rc =      cftau (verb,param)

rc =      cftac (verb,param)

Where:

-   cftau indicates
    that syntax analysis is requested  
    cftac indicates that syntax analysis is not requested
-   &lt;verb> is
    the command that you want to process
-   &lt;param> is
    a character string of variable length that contains the command parameters.
    The end of the field is defined by a character initially set to low-value
-   &lt;rc> is the
    return code

The available &lt;verbs> are listed in the following table.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>&lt;verb&gt;</p></th>
<th><p>Service</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>COM</p></td>
<td><p>Communication mode</p></td>
</tr>
<tr class="even">
<td><p>GETXINFO</p></td>
<td><p>Retrieving information about a transfer made from a synchronous
request</p></td>
</tr>
</tbody>
</table>

The available &lt;param> are listed in the following table.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>&lt;verb&gt;</p></th>
<th><p>&lt;param&gt;</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>com</p>
<p> </p></td>
<td><p>param</p>
<p> </p></td>
<td><p>The COM command parameter structure is as follows: &lt;medium
type&gt; = &lt;Medium name&gt;</p>
<p>The medium type consists in an uppercase letter:</p>
<ul>
<li>'F' for
file</li>
<li>'T' for the TCP/IP synchronous medium</li>
<li>'C' for
the configuration file (ConfigFileName)</li>
</ul>
<p>The medium name is the:</p>
<ul>
<li>Filename,
if the medium type is 'F'</li>
<li>Name
of the communication channel, if the medium type is 'T'</li>
<li>Name
of the configuration file containing the medium of communication characteristics,
if the medium type is C.</li>
</ul></td>
</tr>
<tr class="even">
<td><p>getxinfo</p></td>
<td><p>xinf</p></td>
<td><p>Information about a transfer in the format described in
the cftapi.h file.</p></td>
</tr>
</tbody>
</table>

## Step procedure

Use the COM command to define the synchronous medium.

1.  Open the synchronous communication.
2.  Write the command. This is not specific to synchronous mediums.
3.  Retrieve information using the GETXINFO service.

To view the synchronous communication template containing details and an example, see tcftsyn.

## Return codes

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Mnemonic</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CAPI_NOERR</p></td>
<td><p>No error.</p></td>
</tr>
<tr class="even">
<td><p>CAPI_FUNC_UNDEF</p></td>
<td><p>Command not valid.</p></td>
</tr>
<tr class="odd">
<td><p>CAPI_COM_OPEN</p></td>
<td><p>Communication medium opening error.</p></td>
</tr>
<tr class="even">
<td><p>CAPI_COM_WRITE</p></td>
<td><p>Communication medium write error.</p></td>
</tr>
<tr class="odd">
<td><p>CAPI_COM_CLOSE</p></td>
<td><p>Communication medium closing problem.</p></td>
</tr>
<tr class="even">
<td><p>CAPI_COM_ALLOC</p></td>
<td><p>Communication medium allocation problem.</p></td>
</tr>
<tr class="odd">
<td><p>CAPI_COM_ERR</p></td>
<td><p>Communication medium not available on this system.</p></td>
</tr>
</tbody>
</table>
