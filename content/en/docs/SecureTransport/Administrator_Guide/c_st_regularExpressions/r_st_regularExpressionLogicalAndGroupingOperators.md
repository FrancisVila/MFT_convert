{
    "title": "Logical and grouping operators",
    "linkTitle": "Logical and grouping operators",
    "weight": "350"
}Use these items to match a sequence of characters and indicate subexpressions.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Operator</th>
         <th>Meaning</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code><em>AB</em></code>
         </td>
         <td>Matches pattern <code><em>A</em></code> followed by pattern <em><code>B</code></em>         </td>
      </tr>
      <tr>
         <td><code><em>A</em>|<em>B</em></code>
         </td>
         <td>Matches either pattern <code><em>A</em></code> or pattern <code><em>B</em></code>         </td>
      </tr>
      <tr>
         <td><code>(<em>A</em>)</code>
         </td>
         <td>Groups pattern <code><em>A</em></code> as a subexpression for other operations or for back references         </td>
      </tr>
   </tbody>
</table>
