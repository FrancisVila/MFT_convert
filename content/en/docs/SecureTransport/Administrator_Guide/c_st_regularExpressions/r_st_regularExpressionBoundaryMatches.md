{
    "title": "Boundary matches",
    "linkTitle": "Boundary matches",
    "weight": "330"
}The following table defines boundary matches.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Character class</th>
         <th>Meaning</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>\^</code>
         </td>
         <td>Matches only at the beginning of a line         </td>
      </tr>
      <tr>
         <td><code>\$</code>
         </td>
         <td>Matches only at the end of a line         </td>
      </tr>
      <tr>
         <td><code>\b</code>
         </td>
         <td>Matches only at a word boundary         </td>
      </tr>
      <tr>
         <td><code>\B</code>
         </td>
         <td>Matches only at a non-word boundary         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Transaction Manager automatically places a "<code>\^</code>" at the beginning of the search string and a "<code>\$</code>" at the end of the search string. If you do not want to anchor the regular expression, you must add "<code>.*</code>" to the beginning or end:<br/><code>.*<em>regex</em>.*</code>         </td>
      </tr>
</table>
