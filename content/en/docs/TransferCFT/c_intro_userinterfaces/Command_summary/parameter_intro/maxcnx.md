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

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">On Unix systems, setting the MAXCNX value to higher than 1020  has no impact.          </td>
      </tr>
</table>

[Return to Command index](../../)
