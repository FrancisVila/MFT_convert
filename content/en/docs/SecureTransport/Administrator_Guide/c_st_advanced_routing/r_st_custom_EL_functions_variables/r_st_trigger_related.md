{
    "title": "Trigger related EL for AR",
    "linkTitle": "Trigger related EL for AR",
    "weight": "350"
}The following table provides the trigger related EL expressions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Routing EL expression         </th>
<th class="HeadD-Column1-Header1">Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><code>string getFileContent </code></p>
<p><code>(string filePath, int beginIndex, int length, string charset)</code></p>         </td>
         <td><p>Returns a string that is a sub-string of the file’s content.</p>
<p><em>Example:</em></p>
<p>When the file contains <code>1234567890</code> the <code>getFileContent (file, 1, 3, "UTF8")</code> will return <code>234</code>.</p>         </td>
      </tr>
      <tr>
         <td><p><code>string getFileContentTail </code></p>
<p><code>(string filePath, int beginIndex, int length, string charset)</code></p>         </td>
         <td><p>Returns a string that is a sub-string of the file’s content. The reading of the file begins at the end.</p>
<p><em>Example:</em></p>
<p>When the file contains <code>1234567890</code> the <code>getFileContentTail (file, 1, 3, "UTF8")</code> will return <code>789</code>.</p>         </td>
      </tr>
      <tr>
         <td><p><code>byte[] getFileContentBytes </code></p>
<p><code>(string filePath, int offset, int length) </code></p>         </td>
         <td>Reads up to the specified number of bytes of data starting from a specified offset into an array of bytes from the beginning of the file. An attempt is made to read as many bytes as possible, but a smaller number may be read.         </td>
      </tr>
      <tr>
         <td><p><code>byte[] getFileContentBytesTail </code></p>
<p><code>(string filePath, int offset, int length)</code></p>         </td>
         <td>Reads up to the specified number of bytes of data from a specified offset into an array of bytes starting from the end of the file. An attempt is made to read as many bytes as possible, but a smaller number may be read.         </td>
      </tr>
   </tbody>
</table>

 

The functions which return a string can be used in Expressions and Predicates for route triggering, as well as in other fields in which the expression language is supported.

The functions which return bytes cannot be used in Expressions and Predicates for route triggering. The extraction of file is used for file content composition (for example, trigger file content in a Send To Partner route step).

> **Note:**
>
> When functions which return bytes are used in trigger file content, they cannot be combined with string functions, because bytes will be written.

> **Note:**
>
> The filePath parameter must contain an absolute path and should be written under home folder of the user who is triggering the corresponding route.

 

**Related topics:**

-   <a href="../r_st_session_related" class="MCXref xref">Session related EL for AR</a>
-   <a href="../r_st_predefined_el_functions" class="MCXref xref">Predefined EL functions for AR</a>
-   <a href="../r_st_account_related" class="MCXref xref">Account related EL for AR</a>
-   <a href="../r_st_ldap_related" class="MCXref xref">LDAP related EL for AR</a>
-   <a href="../r_st_pesit_related" class="MCXref xref">PeSIT related EL for AR</a>
-   <a href="../r_st_routing_related" class="MCXref xref">Routing related EL for AR</a>
-   <a href="../r_st_special_routing_variables" class="MCXref xref">Special routing EL variables for AR</a>
-   <a href="../r_st_stfs_pesit_related" class="MCXref xref">STFS PeSIT related EL for AR</a>
-   <a href="../r_st_transfer_related" class="MCXref xref">Transfer related EL for AR</a>
-   <a href="../r_st_user_related" class="MCXref xref">User related EL for AR</a>
-   <a href="../r_st_http_headers" class="MCXref xref">HTTP headers related EL for AR</a>
