{
    "title": "nack",
    "linkTitle": "nack",
    "weight": "2060"
}### nack

#### SEND

\[SEND TYPE = NACK\]

Via negative acknowledgments sent in a PeSIT Hors SIT message, the
final partner signals to the initial sender of the file that application
errors were detected.

If the initial sender does not support this function, the final partner does not transmit the
negative acknowledgement and the Transfer CFT log file displays:

CFTT93W PART=XFB1 IDS=00008 Negative ack not supported by server

#### CFTPROT, CFTPART

\[ NACK = { YES | <u>NO</u> } \]

This parameter enables or disables the NACK feature in either a partner or protocol definition for a non Transfer CFT product.

To enable the use of NACK when connecting to products other than <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>, set the parameter NACK to YES in the CFTPROT or CFTPART objects.

However, note that the CFTPART NACK value overrides the CFTPROT NACK value. If however, this product does not support a negative acknowledgment, the following error message displays in the log: <span class="code"> CFTH13E FPDU Remote reject &lt;PART=STREFSSL DIAGI=909 DIAGP=RCO 301></span>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When performing file transfers between two <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>s, negative acknowledgments are sent regardless of the NACK setting.         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)