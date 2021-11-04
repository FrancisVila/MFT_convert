{
    "title": "Match and replace functions",
    "linkTitle": "Match and replace functions",
    "weight": "340"
}The expression language match and replace functions can match a regular expression or replace it.

The syntax for the replace operation is:

`${variable.replace(<match RE>, <replace RE>)}`

If the match succeeds, the value is the string with the matched string replaced.

The syntax for a match operation is:

`${variable.matches(<match RE>)}`

If the match succeeds, the value is `true`. If it does not, the value is `false`.

> **Note:**
>
> The match operation returns a logical value that can be used with relational or conditional operators.

For more about regular expressions, see <a href="../../c_st_regularexpressions#Appendix_Reg_Ex_3207565968_1044920" class="MCXref xref">Regular expressions</a>.

## Regular expression examples

The following table shows several examples of using the match and replace operations with regular expressions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadE-Column1-Header1">Example         </th>
<th class="HeadD-Column1-Header1">Example return value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Match         </td>
         <td><code>${foo.matches('fo*')}</code>         </td>
         <td><code>true</code>         </td>
      </tr>
      <tr>
         <td>Replace         </td>
         <td><code>${foo.replace('f(.*)', 'm$1')}</code>         </td>
         <td><code>moo</code>         </td>
      </tr>
   </tbody>
</table>
