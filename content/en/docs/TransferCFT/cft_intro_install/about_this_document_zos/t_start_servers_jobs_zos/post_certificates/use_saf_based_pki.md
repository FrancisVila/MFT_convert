{
    "title": "Use SAF-based PKI",
    "linkTitle": "Use SAF-based PKI",
    "weight": "270"
}System Authorization Facility (SAF) based PKI offers a more secure SSL. The optional SAF method uses RACF, or the equivalent, and an optional cryptographic coprocessor to increase data security. To enable the SAF mode of operation you must:

1.  Enable the IBM Crypto Express 2 Coprocessor, if available.
2.  Configure the IBM ICSF program to use a secure PKDS database.
3.  Install and configure the option for Transfer CFT.
4.  Define RACF.

<!-- -->

1.  Define the CFTSSL PARM fields or ROOTCID/USERCID fields.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>A SAF PKI implementation in <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> requires that the ‘ring-specific profile checking' (RDATALIB class) be activated.         </td>
      </tr>
   </tbody>
</table>
