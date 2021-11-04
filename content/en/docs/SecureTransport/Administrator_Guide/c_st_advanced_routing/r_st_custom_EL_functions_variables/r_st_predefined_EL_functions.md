{
    "title": "Predefined EL functions for AR",
    "linkTitle": "Predefined EL functions for AR",
    "weight": "270"
}The following table lists predefined EL functions and descriptions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Syntax         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><code>${variable.toUpperCase()}</code></p>         </td>
         <td><p>Converts given string to upper case only symbols.</p>         </td>
      </tr>
      <tr>
         <td><p><code>${variable.toLowerCase()}</code></p>         </td>
         <td><p>Converts given string to lower case only symbols.</p>         </td>
      </tr>
      <tr>
         <td><p><code>${variable.substring(beginIndex,endIndex)}</code></p>         </td>
         <td><p>Returns a substring for a given string.</p>
<p>The substring begins at the specified beginIndex and
extends to the character at index endIndex - 1.</p>
<p>Thus the length of the substring is endIndex-beginIndex.</p>         </td>
      </tr>
      <tr>
         <td><p><code>${extract(variable, delimiter, position)}</code></p>         </td>
         <td><p>Splits given string to tokens based on a delimiter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">${leadingFolder(path)}</span></p>         </td>
         <td><p>For given directory/file path returns only the leading one.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">${parentFolder(path)}</span></p>         </td>
         <td><p>For given directory/file path returns parent folder path.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">${dayOffset(format, offset)}</span></p>         </td>
         <td><p>Returns a date representing today's date with the offset of the days parameter.</p>         </td>
      </tr>
   </tbody>
</table>

 

The following table lists predefined EL variable functions and <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> examples.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Syntax         </th>
<th class="HeadD-Column1-Header1"><span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> Usage         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><code>${variable.toUpperCase()}</code></p>         </td>
         <td><p><span class="code">${transfer.target.toUpperCase()}</span></p>         </td>
      </tr>
      <tr>
         <td><p><code>${variable.toLowerCase()}</code></p>         </td>
         <td><p><span class="code">${transfer.target.toLowerCase()}</span></p>         </td>
      </tr>
      <tr>
         <td><p><code>${variable.substring(beginIndex,endIndex)}</code></p>         </td>
         <td><p><span class="code">${transfer.target.substring(0,5)}</span></p>         </td>
      </tr>
      <tr>
         <td><p><code>${extract(variable, delimiter, position)}</code></p>         </td>
         <td><p><span class="code">${extract('payroll_Axway_21457584375.txt', '_', 2)}</span>
returns <code>Axway</code></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">${leadingFolder(path)}</span></p>         </td>
         <td><p><span class="code">${leadingFolder('/opt/TMWD/st51')}</span> - returns <span class="code">'opt'</span></p>
<p><span class="code">${leadingFolder('/opt')}</span> - returns <span class="code">'opt'</span></p>
<p><span class="code">${leadingFolder('/')}</span> - returns <span class="code">'/'</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">${parentFolder(path)}</span></p>         </td>
         <td><p><span class="code">${parentFolder(‘/opt/TMWD/st51’)}</span> - returns <code>‘/opt/TMWD’</code></p>
<p><span class="code">${parentFolder(‘/’)}</span> - returns <span class="code">‘/’</span></p>
<p><span class="code">${parentFolder(‘/usr/file.txt’)}</span> - returns <span class="code">‘/usr’</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">${dayOffset(format, offset)}</span></p>         </td>
         <td><p><code>${dayOffset('yyMMdd', '-5')}</code> - returns 10<sup>th</sup> if today is 15<sup>th</sup> of August
formatted as per the specified format parameter - <code>120810</code>.</p>
<p><code>${dayOffset('yyMMdd', '+7')}</code> - returns 22<sup>th</sup> if today is 15<sup>th</sup> of August
formatted as per the specified format parameter - 120822.</p>
<p><code>${dayOffset('ddMMyy', '+1')} ge '090414'}</code></p>         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_session_related" class="MCXref xref">Session related EL for AR</a>
-   <a href="../r_st_account_related" class="MCXref xref">Account related EL for AR</a>
-   <a href="../r_st_ldap_related" class="MCXref xref">LDAP related EL for AR</a>
-   <a href="../r_st_pesit_related" class="MCXref xref">PeSIT related EL for AR</a>
-   <a href="../r_st_routing_related" class="MCXref xref">Routing related EL for AR</a>
-   <a href="../r_st_special_routing_variables" class="MCXref xref">Special routing EL variables for AR</a>
-   <a href="../r_st_stfs_pesit_related" class="MCXref xref">STFS PeSIT related EL for AR</a>
-   <a href="../r_st_transfer_related" class="MCXref xref">Transfer related EL for AR</a>
-   <a href="../r_st_user_related" class="MCXref xref">User related EL for AR</a>
-   <a href="../r_st_http_headers" class="MCXref xref">HTTP headers related EL for AR</a>
