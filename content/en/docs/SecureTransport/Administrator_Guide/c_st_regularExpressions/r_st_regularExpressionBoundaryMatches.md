{
    "title": "Boundary matches",
    "linkTitle": "Boundary matches",
    "weight": "320"
}The following table defines boundary matches.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Character class         </th>
<th class="HeadD-Column1-Header1">Meaning         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>\^</code>         </td>
         <td>Matches only at the beginning of a line         </td>
      </tr>
      <tr>
         <td><code>\$</code>         </td>
         <td>Matches only at the end of a line         </td>
      </tr>
      <tr>
         <td><code>\b</code>         </td>
         <td>Matches only at a word boundary         </td>
      </tr>
      <tr>
         <td><code>\B</code>         </td>
         <td>Matches only at a non-word boundary         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> Transaction Manager automatically places a "\\^" at the beginning of the search string and a "\\$" at the end of the search string. If you do not want to anchor the regular expression, you must add ".\*" to the beginning or end:.\*regex.\*
