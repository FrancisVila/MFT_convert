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
   <thead>
      <tr>
<th colspan="7" class="HeadD-Column1-Header1"><span id="FSPACEX_Table"></span>FSPACEX Table         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
<th class="BodyE-Column1-Body1" data-valign="top" width="17%"><p>OS </p>         </th>
<th class="BodyE-Column1-Body1" data-valign="top" width="10%"><p>PARM </p>         </th>
<th class="BodyE-Column1-Body1" data-valign="top" width="12%"><p>PART </p>         </th>
<th class="BodyE-Column1-Body1" data-valign="top" width="14%"><p>CAT </p>         </th>
<th class="BodyE-Column1-Body1" data-valign="top" width="14%"><p>COM </p>         </th>
<th class="BodyE-Column1-Body1" data-valign="top" width="14%"><p>LOG </p>         </th>
<th class="BodyD-Column1-Body1" data-valign="top" width="20%"><p>ACCNT </p>         </th>
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
