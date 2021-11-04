{
    "title": "maxcnx",
    "linkTitle": "maxcnx",
    "weight": "1880"
}<span id="maxcnx"></span>

### maxcnx

#### CFTNET

\[MAXCNX     = { <u>384</u>
| n} \]      {0...MAXTRANS value up to 2000}

The maximum number of simultaneous connections that <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> accepts
to establish on a given network resource.

-   Enter
    a value between 0 and 2 times the MAXTRANS
    value
-   Recommended value is the same as the MAXTRANS value
-   Default = 384

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>On Unix systems, setting the MAXCNX value to higher than 1020 has no impact.         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
