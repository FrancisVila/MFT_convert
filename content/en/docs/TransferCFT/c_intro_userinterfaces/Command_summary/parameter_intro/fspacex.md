{
    "title": "fspacex",
    "linkTitle": "fspacex",
    "weight": "1360"
}<span id="fspacex"></span>

### fspacex

#### CFTFILE

\[FSPACEX =
{see table below| n}\]

{0..65536}

Depending on TYPE/OS

Secondary allocation of the file to be created expressed in Kbytes
(1024).

The following table indicates for each system the default value
according to the type of file to be created. If the indicated default
value of the secondary allocation of the file to be created is "no",
the FSPACEX does not need to be defined.

<table>
   <th>
      <tr>
<th><span id="FSPACEX_Table"></span>FSPACEX Table         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
<th><p>OS </p>         </th>
<th><p>PARM </p>         </th>
<th><p>PART </p>         </th>
<th><p>CAT </p>         </th>
<th><p>COM </p>         </th>
<th><p>LOG </p>         </th>
<th><p>ACCNT </p>         </th>
      </tr>

      <tr>
         <td><p>z/OS (MVS)</p>         </td>
         <td><p>50 </p>         </td>
         <td><p>100 </p>         </td>
         <td><p>0 </p>         </td>
         <td><p>0 </p>         </td>
         <td><p>50 </p>         </td>
         <td><p>50 </p>         </td>
      </tr>
      <tr>
         <td><p>OS400 </p>         </td>
         <td><p>0 </p>         </td>
         <td><p>0 </p>         </td>
         <td><p>0 </p>         </td>
         <td><p>0 </p>         </td>
         <td><p>0 </p>         </td>
         <td><p>0 </p>         </td>
      </tr>
      <tr>
         <td><p>UNIX </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
      </tr>
      <tr>
         <td><p>Windows</p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
