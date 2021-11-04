{
    "title": "TM server communication rules",
    "linkTitle": "TM server communication rules",
    "weight": "330"
}Network zones define the server ports that the TM Servers running on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers in the secure network connect to on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers running in the peripheral network (DMZ). See <a href="../../../c_st_setup/c_st_networkzones#SetupMenu_1217491348_1149202" class="MCXref xref">Communication across Transaction Manager, protocol, and proxy servers</a>.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">#         </th>
<th class="HeadE-Column1-Header1">Group source         </th>
<th class="HeadE-Column1-Header1">Group destination         </th>
<th class="HeadE-Column1-Header1">Protocol         </th>
<th class="HeadE-Column1-Header1">Destination port         </th>
<th class="HeadE-Column1-Header1">Direction         </th>
<th class="HeadD-Column1-Header1">Purpose         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>22         </td>
         <td>Secure-<br />
Transport<br />
Servers         </td>
         <td>Secure-<br />
Transport<br />
Edge (FTP Server)         </td>
         <td>TCP over SSL         </td>
         <td>20021         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
      <tr>
         <td>23         </td>
         <td>Secure-<br />
Transport<br />
Servers         </td>
         <td>Secure-<br />
Transport<br />
Edge (HTTP Server)         </td>
         <td>TCP over SSL         </td>
         <td>20080         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
      <tr>
         <td>24         </td>
         <td>Secure-<br />
Transport<br />
Servers         </td>
         <td>Secure-<br />
Transport<br />
Edge (AS2 Server)         </td>
         <td>TCP over SSL         </td>
         <td>21080         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
      <tr>
         <td>25         </td>
         <td>Secure-<br />
Transport<br />
Servers         </td>
         <td>Secure-<br />
Transport<br />
Edge (SSH Server)         </td>
         <td>TCP over SSL         </td>
         <td>20022         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
      <tr>
         <td>26         </td>
         <td>Secure-<br />
Transport<br />
Servers         </td>
         <td>Secure-<br />
Transport<br />
Edge (PeSIT Server)         </td>
         <td>TCP over SSL         </td>
         <td>27617         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
      <tr>
         <td>27         </td>
         <td>Secure-<br />
Transport<br />
Servers         </td>
         <td>Administration Tool server         </td>
         <td>TCP over SSL         </td>
         <td>20444         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
   </tbody>
</table>

Do not define these rules in a deployment with no <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge. Define only the rules for the protocols you are using.

Note that in SecureTransport Edge deployment, port 20444 (used by the Administration Tool server) must always be open.

**Related topics:**

-   <a href="../r_st_protocol_rules" class="MCXref xref">Protocol rules</a>
-   <a href="../r_st_authentication_rules" class="MCXref xref">Authentication rules</a>
-   <a href="../r_st_administration_rules" class="MCXref xref">Administration rules</a>
-   <a href="../r_st_server_transfer_rules" class="MCXref xref">Server transfer rules</a>
-   <a href="../r_st_standard_clustering_rules" class="MCXref xref">Standard Cluster rules</a>
-   <a href="../r_st_large_enterprise_clustering_rules" class="MCXref xref">Enterprise Cluster rules</a>
-   <a href="../r_st_protocol_rules_outbound" class="MCXref xref">Protocol rules - outbound from SecureTransport Edge</a>
