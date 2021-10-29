{
    "title": "maxcnx",
    "linkTitle": "maxcnx",
    "weight": "1910"
}### <span id="maxcnx"></span>maxcnx

#### CFTNET

\[MAXCNX     = { <u>384</u>
| n} \]      {0...MAXTRANS value up to 2000}

The maximum number of simultaneous connections that Transfer CFT accepts
to establish on a given network resource.

-   Enter
    a value between 0 and 2 times the MAXTRANS
    value
-   Recommended value is the same as the MAXTRANS value
-   Default = 384

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">On Unix systems, setting the MAXCNX value to higher than 1020 has no impact.         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../)
