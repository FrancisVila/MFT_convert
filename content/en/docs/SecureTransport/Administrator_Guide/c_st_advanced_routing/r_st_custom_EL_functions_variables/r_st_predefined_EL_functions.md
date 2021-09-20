{
    "title": "Predefined EL functions for AR",
    "linkTitle": "Predefined EL functions for AR",
    "weight": "280"
}The following table lists predefined EL functions and descriptions.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Syntax</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p><code>${variable.toUpperCase()}</code>
</p>
         </td>
         <td>
            <p>Converts given string to upper case only symbols.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><code>${variable.toLowerCase()}</code>
</p>
         </td>
         <td>
            <p>Converts given string to lower case only symbols.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><code>${variable.substring(beginIndex,endIndex)}</code>
</p>
         </td>
         <td>
            <p>Returns a substring for a given string.</p>
            <p>The substring begins at the specified beginIndex and 
 extends to the character at index endIndex - 1.</p>
            <p>Thus the length of the substring is endIndex-beginIndex. </p>
         </td>
      </tr>
      <tr>
         <td>
            <p><code>${extract(variable, delimiter, position)}</code>
</p>
         </td>
         <td>
            <p>Splits given string to tokens based on a delimiter.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><span>${leadingFolder(path)}</span>
</p>
         </td>
         <td>
            <p>For given directory/file path returns only the leading one.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><span>${parentFolder(path)}</span>
</p>
         </td>
         <td>
            <p>For given directory/file path returns parent folder path.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><span>${dayOffset(format, offset)}</span>
</p>
         </td>
         <td>
            <p>Returns a date representing today's date with the offset of the days parameter.</p>
         </td>
      </tr>
   </tbody>
</table>

 

The following table lists predefined EL variable functions and Advanced Routing examples.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Syntax</th>
         <th><span>Advanced Routing</span> Usage</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p><code>${variable.toUpperCase()}</code>
</p>
         </td>
         <td>
            <p><span>${transfer.target.toUpperCase()}</span>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><code>${variable.toLowerCase()}</code>
</p>
         </td>
         <td>
            <p><span>${transfer.target.toLowerCase()}</span>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><code>${variable.substring(beginIndex,endIndex)}</code>
</p>
         </td>
         <td>
            <p><span>${transfer.target.substring(0,5)}</span>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><code>${extract(variable, delimiter, position)}</code>
</p>
         </td>
         <td>
            <p><span>${extract('payroll_Axway_21457584375.txt', '_', 2)}</span> 
 returns <code>Axway</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p><span>${leadingFolder(path)}</span>
</p>
         </td>
         <td>
            <p><span>${leadingFolder('/opt/TMWD/st51')}</span> - returns <span>'opt'</span></p>
            <p><span>${leadingFolder('/opt')}</span> - returns <span>'opt'</span></p>
            <p><span>${leadingFolder('/')}</span> - returns <span>'/'</span> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p><span>${parentFolder(path)}</span>
</p>
         </td>
         <td>
            <p><span>${parentFolder(‘/opt/TMWD/st51’)}</span> - returns <code>‘/opt/TMWD’</code></p>
            <p><span>${parentFolder(‘/’)}</span> - returns <span>‘/’</span></p>
            <p><span>${parentFolder(‘/usr/file.txt’)}</span> - returns <span>‘/usr’</span> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p><span>${dayOffset(format, offset)}</span>
</p>
         </td>
         <td>
            <p><code>${dayOffset('yyMMdd', '-5')}</code> - returns 10<sup>th</sup> if today is 15<sup>th</sup> of August 
 formatted as per the specified format parameter - <code>120810</code>.</p>
            <p><code>${dayOffset('yyMMdd', '+7')}</code> - returns 22<sup>th</sup> if today is 15<sup>th</sup> of August 
 formatted as per the specified format parameter - 120822.</p>
            <p><code>${dayOffset('ddMMyy', '+1')} ge '090414'}</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Session related EL for AR](../r_st_session_related)
-   [Account related EL for AR](../r_st_account_related)
-   [LDAP related EL for AR](../r_st_ldap_related)
-   [PeSIT related EL for AR](../r_st_pesit_related)
-   [Routing related EL for AR](../r_st_routing_related)
-   [Special routing EL variables for AR](../r_st_special_routing_variables)
-   [STFS PeSIT related EL for AR](../r_st_stfs_pesit_related)
-   [Transfer related EL for AR](../r_st_transfer_related)
-   [User related EL for AR](../r_st_user_related)
-   [HTTP headers related EL for AR](../r_st_http_headers)
