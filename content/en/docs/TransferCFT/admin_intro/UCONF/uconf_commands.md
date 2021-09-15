{
    "title": "UCONF commands",
    "linkTitle": "UCONF commands",
    "weight": "260"
}You can use the following commands to modify configuration values, check for defaults, or get more information about a parameter. For additional information on the unified configuration, see the section using the [unified configuration utility](..//transfercft/admin_intro/uconf).

**UCONFSET**

Use to modify a technical parameter value.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>UCONFSET id=PARAMETER-KEY,value=STRING         </td>
      </tr>
   </tbody>
</table>

After modifying a uconf value, you typically must restart Transfer CFT. When the parameter flag is set to reconfig (=reconfig), you can use the reconfig command instead of a restart. You can check the parameter flag to see if reconfig is an option for that particular parameter.

Using spaces in a UCONFSET command value

When using CFTUTIL to define a UCONFSET value that contains spaces, the parameter value with spaces must be enclosed by single quotation marks that in turn are within double quotation marks. For example, to define a superuser with spaces use the following format.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL UCONFSET id=am.passport.superuser, value="'A B C D'"         </td>
      </tr>
   </tbody>
</table>

**UCONFGET**

Use to
retrieve a single technical parameter value.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>UCONFGET id=PARAMETER-KEY</p>
         </td>
      </tr>
   </tbody>
</table>

Results: PARAMETER-KEY=PARAMETER-VALUE

**UCONFUNSET**

Use to
return a specified parameter to the default value.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>UCONFUNSET id=PARAMETER-KEY         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Certain uconf values are integrally linked to <b>node</b> type uconf values. If you modify these related values, and then delete the node value, the modified parameters remain in the configuration.          </td>
      </tr>
</table>

**LISTUCONF**

Use to display multiple technical parameter values.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>LISTUCONF id=PARAMETER-KEY-PATTERN,scope=ALL|USER|DEFAULT,content=BRIEF|FULL|DEBUG         </td>
      </tr>
   </tbody>
</table>

RECONFIG TYPE=UCONF

When TYPE=UCONF , the UCONF reconfigurable variables are reloaded. Note that only the UCONF parameters flagged with RECONFIG / IRECONFIG are affected.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Tip  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Tip  &lt;/b&gt;" valign="top">You can use the listuconf content=extract function with fout to extract the configuration with the passwords in clear text (normally passwords are hidden in uconf). Example: <code>CFTUTIL LISTUCONF CONTENT=EXTRACT, FOUT=UCONF</code>         </td>
      </tr>
</table>

Get more information

To get more information on uconf values, enter the command:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>LISTUCONF id=PARAMETER,content=FULL         </td>
      </tr>
   </tbody>
</table>

Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>LISTUCONF id=copilot.general.serverhost,content=FULL         </td>
      </tr>
   </tbody>
</table>
