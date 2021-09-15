{
    "title": "Regular expression characters",
    "linkTitle": "Regular expression characters",
    "weight": "300"
}The following table shows the variables and characters allowed within the regular expressions.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Character</th>
         <th>Meaning</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>unicodeChar         </td>
         <td>Matches any identical Unicode character         </td>
      </tr>
      <tr>
         <td><code> \</code>
         </td>
         <td>Used to quote a meta-character (such as <code>*</code>)         </td>
      </tr>
      <tr>
         <td><code> \\</code>
         </td>
         <td>Matches a single '\' character         </td>
      </tr>
      <tr>
         <td><code> \0<em>nnn</em></code>
         </td>
         <td>Matches a given octal character         </td>
      </tr>
      <tr>
         <td><code> \x<em>hh</em></code>
         </td>
         <td>Matches a given 8-bit hexadecimal character         </td>
      </tr>
      <tr>
         <td><code> \\u<em>hhhh</em></code>
         </td>
         <td>Matches a given 16-bit hexadecimal character         </td>
      </tr>
      <tr>
         <td><code> \t</code>
         </td>
         <td>Matches an ASCII tab character         </td>
      </tr>
      <tr>
         <td><code> \n</code>
         </td>
         <td>Matches an ASCII newline character         </td>
      </tr>
      <tr>
         <td><code> \r</code>
         </td>
         <td>Matches an ASCII return character         </td>
      </tr>
      <tr>
         <td><code> \f</code>
         </td>
         <td>Matches an ASCII form feed character         </td>
      </tr>
   </tbody>
</table>
