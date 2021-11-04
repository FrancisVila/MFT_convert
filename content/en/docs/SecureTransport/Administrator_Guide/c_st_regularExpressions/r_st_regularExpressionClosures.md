{
    "title": "Regular expression closures",
    "linkTitle": "Regular expression closures",
    "weight": "330"
}These match a series of characters by matching the pattern they follow zero or more time.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Character class         </th>
<th class="HeadD-Column1-Header1">Meaning         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>P*</code>         </td>
         <td>Matches the pattern <em><code>P</code></em> zero or more times         </td>
      </tr>
      <tr>
         <td><code>P+</code>         </td>
         <td>Matches the pattern <em><code>P</code></em> one or more times         </td>
      </tr>
      <tr>
         <td><code>P?</code>         </td>
         <td>Matches the pattern <em><code>P</code></em> zero or one times         </td>
      </tr>
      <tr>
         <td><code>P{n}</code>         </td>
         <td>Matches the pattern <em><code>P</code></em> exactly <em><code>n</code></em> times         </td>
      </tr>
      <tr>
         <td><code>P{n,}</code>         </td>
         <td>Matches the pattern <em><code>P</code></em> at least <em><code>n</code></em> times         </td>
      </tr>
      <tr>
         <td><code>P{n,m}</code>         </td>
         <td>Matches the pattern <em><code>P</code></em> at least <em><code>n</code></em> but not more than <em>m</em> times.         </td>
      </tr>
   </tbody>
</table>

All closure operators (`*`, `+`, `?`, `{n,m}`) are *greedy* by default, meaning that they match as many characters of the string as possible without causing the overall match to fail.

A *reluctant* closure matches as few characters of the string as possible without causing the overall match to fail. To specify a reluctant closure, append a `?` to the closure pattern. Valid patterns are `P*?`, `P+?`, and `P??`.
