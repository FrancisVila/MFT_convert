{
    "title": "Expression Language operators",
    "linkTitle": "Expression Languge operators",
    "weight": "280"
}The following operators are supported:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Operator         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>[ ]</code> and <code>.</code>         </td>
         <td>Used to refer to attributes of an object or items in collection.         </td>
      </tr>
      <tr>
         <td><code>+</code>, <code>-</code>, <code>*</code>, <code>/</code> or <code>div</code>, <code>%</code> or <code>mod</code>         </td>
         <td>Arithmetic Operators. Both binary and unary operators are supported         </td>
      </tr>
      <tr>
         <td><code>==</code> or <code>eq</code>, <code>!=</code> or <code>ne</code>, <code>&lt;</code> or <code>lt</code>,<br />
<code>&gt;</code> or <code>gt</code>, <code>&lt;=</code> or <code>le</code>, <code>&gt;=</code> or <code>ge</code>         </td>
         <td>Relational Operators. provides ability to compare values         </td>
      </tr>
      <tr>
         <td><code>&amp;&amp;</code> or <code>and</code>, <code>||</code> or <code>or</code>, <code>!</code> or <code>not</code>         </td>
         <td>Logical Operators         </td>
      </tr>
      <tr>
         <td>empty         </td>
         <td>Empty Operator         </td>
      </tr>
      <tr>
         <td><code>? :</code>         </td>
         <td>Conditional Operator         </td>
      </tr>
   </tbody>
</table>

Parentheses can be used in combination with the operators to change precedence.

{{< SecureTransport/componentshortname  >}} evaluates operators using the following precedence order, listed from highest to lowest and left to right:

-   `[ ] .`
-   `( )`
-   `-` (unary)` not ! empty`
-   `* / div % mod`
-   `+ -` (binary)
-   `< > <= >= lt gt le ge`
-   `== != eq ne`
-   `&& and`
-   `|| or`
-   `? :`
