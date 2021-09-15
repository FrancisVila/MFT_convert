{
    "title": "Partner naming conventions",
    "linkTitle": "Partner naming conventions",
    "weight": "260"
}The parameter setting relative to partners makes a distinction between
the *network* names and *local* names. This
section describes the naming conventions to use in Transfer CFT.

### <span id="Network_names"></span>Network names

The network names are the names the scope of which generally
covers all the communicating partners. Only these names are conveyed over
the network, and must consequently comply with the formats and sizes defined
by the protocols used. The parameters describing these names are described in the following table.

Partner network names

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Object</th>
         <th>Network name</th>
      </tr>
   </thead>
      <tr valign="middle">
         <td valign="top" width="18%">
            <p>NSPART </p>
         </td>
         <td valign="top" width="18%">
            <p>CFTPART </p>
         </td>
         <td valign="top" width="65%">
            <p>Name of the local Transfer CFT with regard to the remote partner 
 described by this command </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="18%">
            <p>NRPART </p>
         </td>
         <td valign="top" width="18%">
            <p>CFTPART </p>
         </td>
         <td valign="top" width="65%">
            <p>Name of the remote partner Transfer CFT </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="18%">
            <p>NPART </p>
         </td>
         <td valign="top" width="18%">
            <p>CFTPARM </p>
         </td>
         <td valign="top" width="65%">
            <p>Default name of the local Transfer CFT with regard 
 to the partners (default value of the NSPART parameter) </p>
         </td>
      </tr>
</table>

### <span id="Local_names"></span>Local names

Local names are limited
to the local Transfer CFT, and are recognized as identifiers specific
to the Transfer CFT. The parameters describing these names are indicated in
the table below:

Partner local names

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Parameter </p>
</th>
         <th>
            <p>Location </p>
</th>
         <th>
            <p>Local name </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>ID </p>
         </td>
         <td>
            <p>CFTPART </p>
         </td>
         <td>
            <p>Uniquely identifies the partner and supplies the default 
 value of the NRPART parameter </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>IPART<br/>parameter setting at requester end </p>
         </td>
         <td>
            <p>CFTPART </p>
         </td>
         <td>
            <p>The local name identifying an intermediate partner 
 (if using store and forward) </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>IPART<br/>during transfer </p>
         </td>
         <td>
            <p>CFT CATALOG </p>
         </td>
         <td>
            <ul>
               <li>If there is no store and forward: remote partner identifier<br/>               </li>
               <li>If there is store and forward: store and forward 
 site identifier (immediate party)                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>PART </p>
         </td>
         <td>
            <p>CFTPARM </p>
         </td>
         <td>
            <p>Identifies the local Transfer CFT </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>PART </p>
         </td>
         <td>
            <p>CFT CATALOG </p>
         </td>
         <td>
            <ul>
               <li>If there is no store and forward: remote partner identifier<br/>               </li>
               <li>If there is store and forward (see the paragraphs below): store and forward 
 site identifier (immediate party).                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>SPART </p>
         </td>
         <td>
            <p>CFT CATALOG </p>
         </td>
         <td>
            <p>Designates the initial sending partner </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>RPART </p>
         </td>
         <td>
            <p>CFT CATALOG </p>
         </td>
         <td>
            <p>Designates the final receiving partner </p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Using_reciprocal_recognition"></span>Using reciprocal recognition

Transfer CFT can use the names in NSPART and NRPART to apply reciprocal
recognition of partners over the network. This recognition mechanism works
by comparing the name that is received from a partner with the name recorded
in the Transfer CFT parameters.

Reciprocal recognition mechanism

The recognition mechanism is displayed
in the diagram below.

<img src="Checks_performed_on_connecting.gif" width="721" height="155" />

*On  the server*, Transfer CFT
also provides the possibility of checking whether the requester
is authorized to connect to the network. This check compares
the requester’s password, set in NSPASSW and conveyed over the network, against
the password indicated in the NRPASSW parameter on the server.

The checks performed on connection are indicated in the following diagram.

<img src="Checks_performed_on_connecting.gif" width="721" height="155" />

That is, a CFTPART parameter is set for each
partner to be communicated with, where different NRPART parameters correspond
to the identifier of these partners, so each partner must identify itself
with a specific unique network identifier.

This principle is applies to this entire section.

However, for requester operations, a partner with the same NRPART
value shows that you can have several partner descriptions
each having the same NRPART value. This is a special operating mode which
should not be generalized.
