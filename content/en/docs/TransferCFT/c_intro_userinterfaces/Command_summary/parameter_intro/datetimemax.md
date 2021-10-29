{
    "title": "datetimemax",
    "linkTitle": "datetimemax",
    "weight": "660"
}### datetimemax

\[ DATETIMEMAX = { 0 | 99123123595999 } \]

Use to display logs that happened on or before this end date and time. Entering 99123123595999 indicates the year 2099 December 31st at 23:59:59.99.

#### LISTCAT, DISPLAY

\[ DATETIMEMAX { <u>0</u> | 99991231235959 } \]

Use to display catalog transfers that happened on or before this end date and time according to the transfer record creation (DATEK, TIMEK). The default value unit is DAY. This parameter accepts either absolute or relative values. Use the syntactical format where:

-   Relative values are: -1, -1M, -1H, -1D
-   Absolute values are: YYYYMMDDhhmmss with a maximum of 14 characters

You can use this parameter in combination with [datetimemin](datetimemin).

Relative example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTUTIL display datetimemax=-2H         </td>
      </tr>
   </tbody>
</table>

Absolute example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTUTIL listcat datetimemax=2021030323         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../)
