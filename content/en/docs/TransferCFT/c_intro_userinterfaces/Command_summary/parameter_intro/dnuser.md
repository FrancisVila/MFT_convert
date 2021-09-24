{
    "title": "dnuser",
    "linkTitle": "dnuser",
    "weight": "790"
}### <span id="dnuser"></span>dnuser

#### CFTSSL

dnuser='(string1, string2)'

Transfer CFT syntax

The new syntax is listed here. For continued compatibility, you can still use
the 2.4.x syntax.

-    
    dnuser=’ (“string1“ Op “string2“)’  
    Where the remote certificate DN must contain string1 Op string2, and Op
    is a OR/OU binary operator or AND/ET binary operator
-    dnuser=’ ( “string1“ Op ! “string2“)’   
    Where the remote certificate DN must contain string1 Op NOT(string2), and
    Op is a  OR/OU binary operator or AND/ET binary operator.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The different attributes of the dnuser or dnissuer string 
 are separated by the '/' character.         </td>
      </tr>
</table>

[Return to Command index](../../)
