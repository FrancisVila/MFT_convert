{
    "title": "Exit  list error messages",
    "linkTitle": "Exit list error messages",
    "weight": "320"
}The error messages stored in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> log
have the following syntax:

CFTT60I PART= &part IDF=
&idf IDT= &idt, &messageLog

<table>
   <th>
      <tr>
<th><p>DiagP<br />
Catalog </p>         </th>
<th><p>&amp;messageLog </p>         </th>
<th><p>Comment </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>- - - </p>         </td>
         <td><p>Exit List V2.4.0 </p>         </td>
         <td><p>Indicates the start of execution of the exit-list program </p>         </td>
      </tr>
      <tr>
         <td><p>EXL RESV </p>         </td>
         <td><p>Err_parameter RESERV </p>         </td>
         <td><p>Error in RESERV parameter of CFTEXIT command</p>
<p>RESERV = 16384 is correct </p>         </td>
      </tr>
      <tr>
         <td><p>EXL FILE </p>         </td>
         <td><p>Err_open criteria file </p>         </td>
         <td><p>Selection criteria file opening error </p>         </td>
      </tr>
      <tr>
         <td><p>EXL CATA </p>         </td>
         <td><p>Err_open catalog file </p>         </td>
         <td><p>Catalog opening error </p>         </td>
      </tr>
      <tr>
         <td><p>EXL LECT </p>         </td>
         <td><p>Err_read catalog file </p>         </td>
         <td><p>Catalog read error </p>         </td>
      </tr>
      <tr>
         <td><p>EXL SYST </p>         </td>
         <td><p>Err_system </p>         </td>
         <td><p>Local system error, cause unknown, generally a problem
of memory allocation </p>         </td>
      </tr>
   </tbody>
</table>

Related topics

-   [Messages
    and error codes](../../../../troubleshoot_intro/messages_and_error_codes_start_here)
