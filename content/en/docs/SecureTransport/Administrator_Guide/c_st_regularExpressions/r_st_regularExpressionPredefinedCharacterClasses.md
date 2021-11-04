{
    "title": "Predefined character classes",
    "linkTitle": "Predefined character classes",
    "weight": "310"
}There is a set of predefined character classes. The following table explains these.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Character class         </th>
<th class="HeadD-Column1-Header1">Meaning         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>.</code>         </td>
         <td>Matches any character other than newline         </td>
      </tr>
      <tr>
         <td><code>\w</code>         </td>
         <td>Matches a "word" character, alphanumeric plus underscore (<code>_</code>)         </td>
      </tr>
      <tr>
         <td><code>\W</code>         </td>
         <td>Matches a non-word character         </td>
      </tr>
      <tr>
         <td><code>\s</code>         </td>
         <td>Matches a whitespace character         </td>
      </tr>
      <tr>
         <td><code>\S</code>         </td>
         <td>Matches a non-whitespace character         </td>
      </tr>
      <tr>
         <td><code>\d</code>         </td>
         <td>Matches a digit character         </td>
      </tr>
      <tr>
         <td><code>\D</code>         </td>
         <td>Matches a non-digit character         </td>
      </tr>
      <tr>
         <td><code>[:alnum:]</code>         </td>
         <td>Alphanumeric characters *         </td>
      </tr>
      <tr>
         <td><code>[:alpha:]</code>         </td>
         <td>Alphabetic characters *         </td>
      </tr>
      <tr>
         <td><code>[:blank:]</code>         </td>
         <td>Space and tab characters *         </td>
      </tr>
      <tr>
         <td><code>[:cntrl:]</code>         </td>
         <td>Control characters *         </td>
      </tr>
      <tr>
         <td><code>[:digit:]</code>         </td>
         <td>Numeric characters *         </td>
      </tr>
      <tr>
         <td><code>[:graph:]</code>         </td>
         <td>Characters that are printable and are also visible. (A space is printable, but not visible, while an "<code>a</code>" is both.) *         </td>
      </tr>
      <tr>
         <td><code>[:javastart:]</code>         </td>
         <td>Start of a Java identifier *         </td>
      </tr>
      <tr>
         <td><code>[:javapart:]</code>         </td>
         <td>Part of a Java identifier *         </td>
      </tr>
      <tr>
         <td><code>[:lower:]</code>         </td>
         <td>Lower-case alphabetic characters *         </td>
      </tr>
      <tr>
         <td><code>[:print:]</code>         </td>
         <td>Printable characters (characters that are not control characters) *         </td>
      </tr>
      <tr>
         <td><code>[:punct:]</code>         </td>
         <td>Punctuation characters (characters that are not letter, digits, control characters, or space characters) *         </td>
      </tr>
      <tr>
         <td><code>[:space:]</code>         </td>
         <td>Space characters (for example, space, tab, and form feed) *         </td>
      </tr>
      <tr>
         <td><code>[:upper:]</code>         </td>
         <td>Upper-case alphabetic characters *         </td>
      </tr>
      <tr>
         <td><code>[:xdigit:]</code>         </td>
         <td>Characters that are hexadecimal digits *         </td>
      </tr>
      <tr>
         <td><code>\p{Alnum}</code>         </td>
         <td>Alphanumeric characters †         </td>
      </tr>
      <tr>
         <td><code>\p{Alpha}</code>         </td>
         <td>Alphabetic characters †         </td>
      </tr>
      <tr>
         <td><code>\p{Blank}</code>         </td>
         <td>Space and tab characters †         </td>
      </tr>
      <tr>
         <td><code>\p{Cntrl}</code>         </td>
         <td>Control characters †         </td>
      </tr>
      <tr>
         <td><code>\p{Digit}</code>         </td>
         <td>Numeric characters †         </td>
      </tr>
      <tr>
         <td><code>\p{Graph}</code>         </td>
         <td>Characters that are printable and are also visible. (A space is printable, but not visible, while an "<code>a</code>" is both.) †         </td>
      </tr>
      <tr>
         <td><code>\p{Lower}</code>         </td>
         <td>Lower-case alphabetic characters †         </td>
      </tr>
      <tr>
         <td><code>\p{Print}</code>         </td>
         <td>Printable characters (characters that are not control characters) †         </td>
      </tr>
      <tr>
         <td><code>\p{Punct}</code>         </td>
         <td>Punctuation characters (characters that are not letter, digits, control characters, or space characters) †         </td>
      </tr>
      <tr>
         <td><code>\p{Space}</code>         </td>
         <td>Space characters (for example, space, tab, and form feed) †         </td>
      </tr>
      <tr>
         <td><code>\p{Upper}</code>         </td>
         <td>Upper-case alphabetic characters †         </td>
      </tr>
      <tr>
         <td><code>\p{Xdigit}</code>         </td>
         <td>Characters that are hexadecimal digits †         </td>
      </tr>
   </tbody>
</table>

\* For regular expressions used with the Transaction Manager rule `~ (match)` operator see LDAP domain DN filter (see <a href="../../c_st_authentication/t_st_ldapsettings/t_st_manage_dn_filters_for_domain#Manage" class="MCXref xref">Manage DN filters for a domain</a>).

† For all other regular expressions.
