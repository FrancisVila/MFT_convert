{
    "title": "Trigger related EL for AR",
    "linkTitle": "Trigger related EL for AR",
    "weight": "360"
}The following table provides the trigger related EL expressions.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Routing EL expression</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p><code>string getFileContent <br/></code>
</p>
            <p><code>(string filePath, int beginIndex, int length, string charset)</code>
</p>
         </td>
         <td>
            <p>Returns a string that is a sub-string of the file’s content.</p>
            <p><i>Example:</i>
</p>
            <p>When the file contains <code>1234567890</code> the <code>getFileContent (file, 1, 3, "UTF8")</code> will return <code>234</code>.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><code>string getFileContentTail </code>
</p>
            <p><code>(string filePath, int beginIndex, int length, string charset)</code>
</p>
         </td>
         <td>
            <p>Returns a string that is a sub-string of the file’s content. The reading of the file begins at the end.</p>
            <p><i>Example:</i>
</p>
            <p>When the file contains <code>1234567890</code> the <code>getFileContentTail (file, 1, 3, "UTF8")</code> will return <code>789</code>.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><code>byte[] getFileContentBytes </code>
</p>
            <p><code>(string filePath, int offset, int length) </code>
</p>
         </td>
         <td>Reads up to the specified number of bytes of data starting from a specified offset into an array of bytes from the beginning of the file. An attempt is made to read as many bytes as possible, but a smaller number may be read.         </td>
      </tr>
      <tr>
         <td>
            <p><code>byte[] getFileContentBytesTail </code>
</p>
            <p><code>(string filePath, int offset, int length)</code>
</p>
         </td>
         <td>Reads up to the specified number of bytes of data from a specified offset into an array of bytes starting from the end of the file. An attempt is made to read as many bytes as possible, but a smaller number may be read.         </td>
      </tr>
   </tbody>
</table>

 

The functions which return a string can be used in Expressions and Predicates for route triggering, as well as in other fields in which the expression language is supported.

The functions which return bytes cannot be used in Expressions and Predicates for route triggering. The extraction of file is used for file content composition (for example, trigger file content in a Send To Partner route step).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When  functions which return bytes are used in trigger file content, they cannot be combined with string functions, because bytes will be written.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <code>filePath</code> parameter must contain an absolute path and should be written under home folder of the user who is triggering the corresponding route.         </td>
      </tr>
</table>

 

**Related topics:**

-   [Session related EL for AR](../r_st_session_related)
-   [Predefined EL functions for AR](../r_st_predefined_el_functions)
-   [Account related EL for AR](../r_st_account_related)
-   [LDAP related EL for AR](../r_st_ldap_related)
-   [PeSIT related EL for AR](../r_st_pesit_related)
-   [Routing related EL for AR](../r_st_routing_related)
-   [Special routing EL variables for AR](../r_st_special_routing_variables)
-   [STFS PeSIT related EL for AR](../r_st_stfs_pesit_related)
-   [Transfer related EL for AR](../r_st_transfer_related)
-   [User related EL for AR](../r_st_user_related)
-   [HTTP headers related EL for AR](../r_st_http_headers)
