{
    "title": "Synchronous communication services in COBOL",
    "linkTitle": "Synchronous communication services in COBOL",
    "weight": "370"
}# <span id="Synchronous_communication_services_in_COBOL"></span>Synchronous communication services

This topic describes Transfer CFT synchronous communication services.

## Description of functions

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Function</p>
</th>
         <th>
            <p>Use</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p>COM</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Set the communication medium</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>GETXINFO</p>
         </td>
         <td>
            <p>Retrieve information concerning the last transfer made 
 from a synchronous request after a request of the following types: SEND, 
 RECV, HALT, KEEP, START, RESUME, DELETE, END, SUBMIT, SWITCH, PURGE.</p>
            <p>The information is stored in a cftApiInf-type structure:</p>
            <ul>
               <li>Transfer 
 state                </li>
               <li>Diagnostic 
                </li>
               <li>Diagnostic 
 protocol                </li>
               <li>Value 
 of the PART field of CFTPARM                </li>
               <li>Transfer 
 identifier (IDT)                </li>
               <li>Local 
 transfer identifier (IDTU)                </li>
               <li>Transfer 
 type (single, cyclical, diffusion list, collection, file group)                </li>
               <li>Public 
 reference of the transfer (only for a single transfer in Send)               </li>
            </ul>
            <p>The GETXINFO action returns an error if the communication 
 medium is not synchronous.</p>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The public 
 reference of the transfer is a character string of variable length. In 
 the PESIT protocol, it contains 'pi13.pi3.pi4.pi11.pi12.pi61.pi62'.         </td>
      </tr>
</table></p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="Call Syntax"></span>Call syntax

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CALL     "CFTU"     
 USING     &lt;verb&gt;       &lt;param&gt;     
 &lt;rc&gt;<br/>CALL     "CFTC"     
 USING     &lt;verb&gt;       &lt;param&gt;     
 &lt;rc&gt;         </td>
      </tr>
   </tbody>
</table>

Where:

-   CFTU indicates
    that syntax analysis is requested  
    CFTC indicates that syntax analysis is not requested
-   &lt;verb> is
    the command that you want to process
-   &lt;param> is
    a character string of variable length that contains the command parameters.
    The end of the field is defined by a character initially set to low-value
-   &lt;rc> is the
    return code

The available &lt;verbs> are listed in the following table.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td bgcolor="#C0C0C0" valign="top" width="25.025%">
            <p><b>&lt;verb&gt;</b>
</p>
         </td>
         <td bgcolor="#C0C0C0" colspan="1" rowspan="1" valign="top" width="15.389%">
            <p><b>Value</b>
</p>
         </td>
         <td bgcolor="#C0C0C0" valign="top" width="59.586%">
            <p><b>Service</b>
</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="25.025%">
            <p>F-COM</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="15.389%">
            <p>COM</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="59.586%">
            <p>Communication mode</p>
         </td>
      </tr>
</table>

The available &lt;param> are listed in the following table.

<table bgcolor="#FFFFFF" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td bgcolor="#C0C0C0" valign="top" width="20.005%">
            <p>&lt;verb&gt;</p>
         </td>
         <td bgcolor="#C0C0C0" colspan="1" rowspan="1" valign="top" width="18.644%">
            <p>&lt;param&gt;</p>
         </td>
         <td bgcolor="#C0C0C0" valign="top" width="61.351%">
            <p>Explanation</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="20.005%">
            <p>F-COM</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="18.644%">
            <p>D-COM</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="61.351%">
            <p>The COM command parameter structure is as follows: &lt;medium 
 type&gt; = &lt;Medium name&gt;</p>
            <p>The medium type consists in an uppercase letter:</p>
            <ul>
               <li>'F' for 
 file               </li>
               <li>'T' 
 for the TCP/IP synchronous medium               </li>
               <li>'C' for 
 the configuration file (ConfigFileName)               </li>
            </ul>
            <p>The medium name is the:</p>
            <ul>
               <li>Filename, 
 if the medium type is 'F'               </li>
               <li>Name 
 of the communication channel, if the medium type is 'T'               </li>
               <li>Name 
 of the configuration file containing the medium of communication characteristics, 
 if the medium type is C.                </li>
            </ul>
         </td>
      </tr>
</table>

## Return codes

<table bgcolor="#FFFFFF" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Mnemonic</p>
</th>
         <th>
            <p>Description</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="31.895%">
            <p>CAPI-NOERR</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="68.105%">
            <p>No error</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="31.895%">
            <p>CAPI-FUNC-UNDEF</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="68.105%">
            <p>Command not valid</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="31.895%">
            <p>CAPI-COM-OPEN</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="68.105%">
            <p>Communication medium opening error</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="31.895%">
            <p>CAPI-COM-WRITE</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="68.105%">
            <p>Communication medium write error</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="31.895%">
            <p>CAPI-COM-CLOSE</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="68.105%">
            <p>Communication medium closing problem</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="31.895%">
            <p>CAPI-COM-ALLOC</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="68.105%">
            <p>Communication medium allocation problem</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="31.895%">
            <p>CAPI-COM-ERR</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="68.105%">
            <p>Communication medium not available on this system</p>
         </td>
      </tr>
   </tbody>
</table>

The available &lt;verbs> are
listed in the following table.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>&lt;verb&gt;</p>
</th>
         <th>
            <p>Value</p>
</th>
         <th>
            <p>Service</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="25.025%">
            <p>F-COM</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="15.389%">
            <p>COM</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="59.586%">
            <p>Communication mode</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="25.025%">
            <p>F-GETINXFO</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="15.389%">
            <p>GETINXFO</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="59.586%">
            <p>Recovering information about a transfer made from a synchronous 
 request</p>
         </td>
      </tr>
   </tbody>
</table>

The available &lt;param> are
listed in the following table.

<table bgcolor="#FFFFFF" cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>&lt;verb&gt;</p>
</th>
         <th>
            <p>&lt;param&gt;</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="20.005%">
            <p>F-COM</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="18.644%">
            <p>D-COM</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="61.351%">
            <p>The COM command parameter structure is as follows: &lt;medium 
 type&gt; = &lt;Medium name&gt;</p>
            <p>The medium type consists in an uppercase letter:</p>
            <ul>
               <li>'F' for 
 file               </li>
               <li>'T' for the TCP/IP synchronous medium               </li>
               <li>'C' for 
 the configuration file (ConfigFileName)               </li>
            </ul>
            <p>The medium name is the:</p>
            <ul>
               <li>Filename, 
 if the medium type is 'F'               </li>
               <li>Name 
 of the communication channel, if the medium type is 'T'               </li>
               <li>Name 
 of the configuration file containing the medium of communication characteristics, 
 if the medium type is C.                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="20.005%">
            <p>F-GETINXFO</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="18.644%">
            <p>Z-XINF</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="61.351%">
            <p>Information about a transfer in the format described in 
 the <span>OAPIINF</span> file.</p>
         </td>
      </tr>
   </tbody>
</table>
