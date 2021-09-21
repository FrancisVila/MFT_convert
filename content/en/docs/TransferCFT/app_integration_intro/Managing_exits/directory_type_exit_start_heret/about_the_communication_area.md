{
    "title": "About the communication area",
    "linkTitle": "About the communication area",
    "weight": "350"
}# <span id="Title"></span><span id="About_the_communication_area___directory_exit"></span>About the communication area

This topic describes the communication area structure. The communication
area contains:

-   [General
    information fields](#general_information_fields)
-   [Return
    codes](#return_codes___directory_exit)
-   [Partner
    information](#partner_information___directory_exit)
-   [Partner
    network information](#partner_network_information___directory_exit)
-   [Information
    per network type](#partner_network_information___directory_exit) (not supported by all networks)

The next topic describes the communication area structure between the
interface and the user program.

The following tables list all the fields of the communication structure.

### <span id="General_information_fields"></span>General information fields

<table bgcolor="#FFFFFF" cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr>
         <td bgcolor="#C0C0C0" colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>Field</p>
         </td>
         <td bgcolor="#C0C0C0" colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Explanation</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>version </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Interface 
 version number</p>
            <p>The current version 
 number is "0130".</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>idexit </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>EXIT task 
 identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>exname</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>User name</p>
            <p>The user name is equal to the value of the exaref parameter 
 of the exaini function.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>parm</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>User parameter</p>
            <p>The user parameter 
 is equal to the value of the PARM parameter of the CFTEXIT object.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>exver</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Exit version V24 or higher</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>language</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Language 
 of the user program:</p>
            <ul>
               <li>C: C 
 language               </li>
               <li>O: COBOL 
                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>etype</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>EXIT task 
 type</p>
            <p>A: directory Exit</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>etrace</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Inoperative 
 parameter</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>mode</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Call mode:</p>
            <ul>
               <li>R: Requester 
 mode               </li>
               <li>S: Server 
 mode               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>commutfl</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Switching 
 flag (intermediate partner):</p>
            <ul>
               <li>0: no 
 switching in process               </li>
               <li>1: switching 
 in process               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>curtime</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Current 
 time (HHMMSSCC)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>curdate</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Current date (YYYYMMDD)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>curreqc</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Current number of transfers in requester 
 mode for the given network partner</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>cursrvc</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Current number of transfers in server 
 mode for the given network partner</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>maxrty</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Requester mode only</p>
            <p>Maximum number of network connection attempts</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>currty</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Requester 
 mode only</p>
            <p>Current number of network connection attempts</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>maxrtyp </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Requester 
 mode only</p>
            <p>Maximum 
 number of protocol connection attempts</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>currtyp</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Requester 
 mode only</p>
            <p>Current 
 number of protocol connection attempts</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>protl </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Information about the protocols of the CFTPARM object:</p>
            <ul>
               <li>protocol 
 identifier               </li>
               <li>protocol 
 type               </li>
               <li>profile, 
 in the case of the PESIT protocol               </li>
               <li>associated 
 network type               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>idf </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Partner-related 
 file identifier</p>
         </td>
      </tr>
</table>

### <span id="Return_codes___directory_exit"></span>Return codes

<table bgcolor="#FFFFFF" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>ret1</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Return 
 code</p>
            <ul>
               <li>0: Processing 
 ok               </li>
               <li>1: Transfer 
 CFT must take charge of the call               </li>
               <li>2: Connection 
 refusal               </li>
               <li>9: Processing 
 error               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>ret2 </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Cause 
 of connection refusal if the return code value is 2</p>
            <ul>
               <li>1: Partner 
 not known               </li>
               <li>2: Password 
 not valid               </li>
               <li>3: Address 
 not known               </li>
               <li>4: Call 
 time not valid               </li>
               <li>5: Communication 
 protocol not valid               </li>
               <li>6: Maximum 
 number of virtual circuits reached               </li>
               <li>7: Maximum 
 number of transfers reached               </li>
               <li>8: Maximum 
 number of partners reached               </li>
               <li>9: Caller 
 taxation refusal               </li>
               <li>10: Network 
 problem               </li>
               <li>255: 
 Other cause of connection refusal               </li>
            </ul>
            <p>These refusal codes are converted by  <span>Transfer CFT</span> into 
 internal diagnostic codes.</p>
            <p>In 
 server mode, the internal diagnostic codes are converted into 
 protocol diagnostic codes and sent to the calling partner.</p>
            <p>In 
 requester mode, the internal diagnostic codes are saved in 
 the catalog.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>diag</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Diagnostic 
 code if the return code is not 0 and 1</p>
            <p>The contents of this field are used in the EXIT related 
 error.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>msg </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>User message</p>
            <p>If this field is defined, the content is sent to the Transfer 
 CFT standard output.</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Partner_information___directory_exit"></span>Partner information

<table bgcolor="#FFFFFF" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>ptype</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Partner 
 type:</p>
            <ul>
               <li>C: normal 
  <span>Transfer CFT</span> partner               </li>
               <li>D: dynamic 
  <span>Transfer CFT</span> partner               </li>
               <li>E: non 
  <span>Transfer CFT</span> partner               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>part</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Partner 
 local identifie</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>ipart</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Intermediate partner local identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>cpart</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Associated store and forward partner identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>idnet</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Network resource identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>idprot</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Protocol identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>prot</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Protocol type:</p>
            <ul>
               <li>P: PeSIT 
 protocol               </li>
               <li>0: ODETTE 
 protocol               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>prof</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>PeSIT 
 only</p>
            <p>Profile:</p>
            <ul>
               <li>C : PeSIT 
 D, Cft               </li>
               <li>S: PeSIT 
 D, Sit               </li>
               <li>A: PeSIT 
 E               </li>
               <li>D: PeSIT 
 E (DMZ)               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>syst</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Operating 
 system:</p>
            <ul>
               <li>4: OS400 
                </li>
               <li>7: GCOS7 
                </li>
               <li>8: GCOS8 
                </li>
               <li>M: MVS 
 
                </li>
               <li>S: UNIX 
                </li>
               <li>V: VMS 
                </li>
               <li>G: GUARD 
                </li>
               <li>B: BS2000 
                </li>
               <li>W: WINDOWS 
                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>code </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Code:</p>
            <ul>
               <li>A:  ASCII               </li>
               <li>E:  EBCDIC               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>open</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>No longer supported</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>commut</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Store 
 and forward indicator:</p>
            <ul>
               <li>N:  No 
 store and forward               </li>
               <li>Y: Immediate 
 store and forward               </li>
               <li>S: Deferred 
 store and forward               </li>
               <li>P: Forced 
 commutation                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>sap</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Remote 
 SAP (Service Access Point)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>imaxtime</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Maximum incoming call time (HHMMSSCC)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>imintime</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Minimum incoming call time (HHMMSSCC)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>omaxtime</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Maximum outgoing call time (HHMMSSCC)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>omintime</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Minimum outgoing call time (HHMMSSCC)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>nrpart</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Remote partner name</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>nrpassw</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Remote partner password</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>newnrpw</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>PeSIT E only</p>
            <p>Remote partner new password </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>nspart</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Local name</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>nspassw</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Local password</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>newnspw</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>PeSIT E only</p>
            <p>New local password</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>group</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Group identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>sauth</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>File send authorization list identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>rauth</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>File receive authorization list identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>xlate</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Transcoding table identifier</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Partner_network_information___directory_exit"></span>Partner network information

<table bgcolor="#FFFFFF" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>ntype</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Network 
 type:</p>
            <ul>
               <li>T: TCP 
                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>addr</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Remote 
 partner address</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>imaxt</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Maximum incoming call time on the network 
 resource</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>imint</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Minimum incoming call time on the network 
 resource</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>omaxt </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Maximum outgoing call time on the network 
 resource</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>omint</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Minimum outgoing call time on the network 
 resource</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>retryw</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Spacing of connection attempts (in minutes)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>retryn</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Number of connection attempts spaced by 
 retryw</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>retrym</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Maximum number of connection attempts</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>cnxin</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Maximum number of simultaneous incoming 
 calls for the given network partner</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>cnxout</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Maximum number of simultaneous outgoing 
 calls, for the given network partner</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>cnxinout</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Maximum number of simultaneous communications, 
 for the given network partner</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Network_dependent_information___directory_exit"></span>Network dependent information

<table bgcolor="#FFFFFF" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>udata</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>User data</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>odata</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Other data. </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>speedin</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Virtual 
 circuit input speed (in bits/second)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>speedout</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Virtual circuit output speed (in bits/second)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>pcvin</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Incoming reverse charge call:</p>
            <ul>
               <li>1: Yes               </li>
               <li>0: No               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>pcvout</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Outgoing 
 reverse charge call:</p>
            <ul>
               <li>1: Yes               </li>
               <li>0: No               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>gfa</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Closed 
 subscriber group number</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>verify</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Number of characters (between 0 and 64) 
 to be checked in the caing partner address</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>parity</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Obsolete parameter</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>databit</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Obsolete parameter</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>stopbit</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Obsolete parameter</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>modout</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Obsolete parameter</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>config</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Obsolete parameter</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>padno</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Obsolete parameter</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>padset</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Obsolete parameter</p>
         </td>
      </tr>
   </tbody>
</table>

### Additional information

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p>cMode</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL mode Client/Server</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>cAuthPolicy</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL auth Anonymous/Simple/Double</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>bCipher</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL cipher suite</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sParm</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL command free parameters</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteUserDn</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Remote User certificate Dn</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteIssuerDn</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Remote Issuer Dn</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteCaId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Remote CA Alias</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sUserCId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>User Certificate Alias</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sCertFname</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File including Remote certificate</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sProf</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL profile ID</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteSerial</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Serial Number</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ExitFree</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Free Area between all EXITs</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>XferCycleId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>CycleId for tracking occurrences </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>XferObjectcId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name of the transfer tracking class </p>
         </td>
      </tr>
   </tbody>
</table>
