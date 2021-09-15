{
    "title": "Match and replace functions",
    "linkTitle": "Match and replace functions",
    "weight": "350"
}The expression language match and replace functions can match a regular expression or replace it.

The syntax for the replace operation is:

`${variable.replace(<match RE>, <replace RE>)}`

If the match succeeds, the value is the string with the matched string replaced.

The syntax for a match operation is:

`${variable.matches(<match RE>)}`

If the match succeeds, the value is `true`. If it does not, the value is `false`.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The match operation returns a logical value that can be used with relational or conditional operators.         </td>
      </tr>
</table>

For more about regular expressions, see [Regular expressions](../../c_st_regularexpressions).

## Regular expression examples

The following table shows several examples of using the match and replace operations with regular expressions.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Name</th>
         <th>Example</th>
         <th>Example return value</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Match         </td>
         <td><code>${foo.matches('fo*')}</code>
         </td>
         <td><code>true</code>
         </td>
      </tr>
      <tr>
         <td>Replace         </td>
         <td><code>${foo.replace('f(.*)', 'm$1')}</code>
         </td>
         <td><code>moo</code>
         </td>
      </tr>
   </tbody>
</table>
