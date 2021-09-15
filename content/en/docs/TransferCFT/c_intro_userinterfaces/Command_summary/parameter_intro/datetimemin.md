{
    "title": "datetimemin",
    "linkTitle": "datetimemin",
    "weight": "670"
}### datetimemin

#### LISTLOG

\[ DATETIMEMIN { <u>0</u> | 99123123595999 } \]

Use to display logs that happened on or after this start date and time. The default of <u>0</u> indicates no check.

#### LISTCAT, DISPLAY

\[ DATETIMEMIN { 0 | 99991231235959 } \]

Use to display catalog transfers that happened on or after this start date and time according to the transfer record creation (DATEK, TIMEK). The default value unit is DAY. This parameter accepts either absolute or relative values. Use the syntactical format where:

-   Relative values are: -1, -1M, -1H, -1D
-   Absolute values are: YYYYMMDDhhmmss with a maximum of 14 characters

You can use this parameter in combination with [datetimemax](../datetimemax).

Relative example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL display datetimemin=-3H         </td>
      </tr>
   </tbody>
</table>

Absolute example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL listcat datetimemin=2021030420         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
