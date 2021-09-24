{
    "title": "CFTIDF - Template/virtual file association",
    "linkTitle": "CFTIDF - Template/virtual file association",
    "weight": "380"
}# <span id="kanchor18"></span><span id="CFTIDF"></span>CFTIDF - Template to virtual file association

<span id="About_the_CFTIDF_Command"></span>You can use this command to locally establish this correspondence
between the local IDF and the NIDF sent or received.

Related
topics

-   Command syntax
    [CFTIDF](../../../command_summary)
-   Object concepts
    [Template
    to virtual file association](../../../../concepts/cft_configuration_concepts_start_here/network_file_identifier_concepts)

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter </th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/id">ID</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Local identifier of the file on the local site (IDF).</p>
            <p>This identifier corresponds to the value of the ID parameter 
 of the CFTSEND/CFTRECV command or to the IDF parameter of the SEND/RECV 
 command.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/nidf">NIDF</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File network identifier; value which is sent over the network.</p>
            <p>It is not possible, for the direction of a given transfer, 
 to have multiple CFTIDF commands with an identical NIDF.</p>
            <p>Note: 
 In 
 standard PeSIT E, the NIDF is transported in the PI 12 (14 
 characters maximum). In PeSIT E between 2 Transfer CFTs, 
 if the NIDF is longer than 14 characters, this NIDF is transported in 
 the PI 99 (28 characters maximum), the value indicated in the PI 12 being 
 truncated to 14 characters.</p>
            <p>string14PeSIT 
 E</p>
            <p>string28  PeSIT 
 E CFT/CFT</p>
            <p>string26  ODETTE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/part">PART</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Local identifier of the partner for which the IDF/NIDF 
 correspondence is valid.</p>
            <p>Same value as the value of the ID parameter of CFTPART.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/type">TYPE</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer direction for which this correspondence is valid.</p>
            <p>The values indicated are:</p>
            <ul>
               <li>SEND 
 for send transfers               </li>
               <li>RECV 
 for receive transfers               </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>
