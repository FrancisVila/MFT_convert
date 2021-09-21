{
    "title": "Specific Transfer CFT configurations",
    "linkTitle": "Specific Transfer CFT configurations",
    "weight": "250"
}# <span id="Specialized_UNIX_configurations"></span>Unix-specific values

This topic summarizes Transfer CFT characteristics that differ from
other operating systems:

-   specific values
-   default files
-   filename extensions

## Specific values tables

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Notation</th>
         <th>Object</th>
         <th>Value</th>
      </tr>
   </thead>
      <tr valign="middle">
         <td valign="top" width="17%">
            <p>char_file </p>
         </td>
         <td valign="top" width="51%">
            <p>Prefix to logical names </p>
         </td>
         <td valign="top" width="32%">
            <p>_ (underlined) </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="17%">
            <p>char_mask </p>
         </td>
         <td valign="top" width="51%">
            <p>Wild card character </p>
         </td>
         <td valign="top" width="32%">
            <p>? </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="17%">
            <p>char_unit </p>
         </td>
         <td valign="top" width="51%">
            <p>Separator (volume) </p>
         </td>
         <td valign="top" width="32%">
            <p>none </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="17%">
            <p>char_symb </p>
         </td>
         <td valign="top" width="51%">
            <p>Prefix to symbolic variables </p>
         </td>
         <td valign="top" width="32%">
            <p>&amp; </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="17%">
            <p>char_directory </p>
         </td>
         <td valign="top" width="51%">
            <p>Character introduced in the path name of the FNAME parameter 
 (CFTRECV) from which a tree structure can be created </p>
         </td>
         <td valign="top" width="32%">
            <p>+ </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="17%">
            <p>file_symb </p>
         </td>
         <td valign="top" width="51%">
            <p>Character introducing a file name sent to CFTUTIL in parameter 
 form </p>
         </td>
         <td valign="top" width="32%">
            <p>@ </p>
         </td>
      </tr>
</table>

## Names of default files used by CFTUTIL

<table border="1" bordercolordark="#c0c0c0" bordercolorlight="#c0c0c0" cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p><b>Objet</b> </p>
</th>
         <th>
            <p><span>Default name</span> </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="middle">
         <td valign="top" width="34%">
            <p>Parameters file </p>
         </td>
         <td valign="top" width="66%">
            <p>_CFTPARM </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="34%">
            <p>Partners file </p>
         </td>
         <td valign="top" width="66%">
            <p>_CFTPART </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="34%">
            <p>Catalogc file </p>
         </td>
         <td valign="top" width="66%">
            <p>_CFTCATA </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="34%">
            <p>Log file </p>
         </td>
         <td valign="top" width="66%">
            <p>_CFTLOG </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="34%">
            <p>Communication media </p>
         </td>
         <td valign="top" width="66%">
            <p>_CFTCOM  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="34%">
            <p>statistics file </p>
         </td>
         <td valign="top" width="66%">
            <p>_CFTACNT </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="34%">
            <p>Preferred media </p>
         </td>
         <td valign="top" width="66%">
            <p>File </p>
         </td>
      </tr>
   </tbody>
</table>
