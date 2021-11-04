{
    "title": "dnuser",
    "linkTitle": "dnuser",
    "weight": "760"
}<span id="dnuser"></span>

### dnuser

#### CFTSSL

dnuser='(string1, string2)'

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> syntax

The new syntax is listed here. For continued compatibility, you can still use
the 2.4.x syntax.

-    
    dnuser=’ (“string1“ Op “string2“)’  
    Where the remote certificate DN must contain string1 Op string2, and Op
    is a OR/OU binary operator or AND/ET binary operator
-    dnuser=’ ( “string1“ Op ! “string2“)’   
    Where the remote certificate DN must contain string1 Op NOT(string2), and
    Op is a  OR/OU binary operator or AND/ET binary operator.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The different attributes of the dnuser or dnissuer string
are separated by the '/' character.         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
