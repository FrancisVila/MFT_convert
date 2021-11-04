{
    "title": "Predefined functions",
    "linkTitle": "Predefined functions",
    "weight": "300"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> supports the following predefined functions:

<table>
   <thead>
      <tr>
<th colspan="2" class="HeadD-Column1-Header1">Name Syntax         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Date<code>${date()}</code><br />
or<br />
<code>${date(date-and-time-pattern)}</code>         </td>
      </tr>
      <tr>
         <td>dayOffset <code>${dayOffset('yymmdd', 'var1')}</code>         </td>
      </tr>
      <tr>
         <td>Random ID<code>${random()}</code>         </td>
      </tr>
      <tr>
         <td>String Concatenation<code>${concat(var1, var2)}</code>         </td>
      </tr>
      <tr>
         <td>Substring <code>${substring(variable, beginIndex,endIndex)}</code>         </td>
      </tr>
      <tr>
         <td>Force Exception<code>${error()}</code> or <code>${error(message)}</code>         </td>
      </tr>
      <tr>
         <td>File Name<code>${filename(variable)}</code>         </td>
      </tr>
      <tr>
         <td>File Basename<code>${basename(variable)}</code>         </td>
      </tr>
      <tr>
         <td>File Extension<code>${extension(variable)}</code>         </td>
      </tr>
      <tr>
         <td><code>${resolve()}</code>         </td>
      </tr>
   </tbody>
</table>

## Predefined function examples

The following table shows examples of the predefined functions:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadE-Column1-Header1">Example usage         </th>
<th class="HeadD-Column1-Header1">Example return value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Date (default)         </td>
         <td><code>${date()}</code>         </td>
         <td><code>June 22, 2012 1:42:04 AM</code>         </td>
      </tr>
      <tr>
         <td>Date (formatted)         </td>
         <td><code>${date('EEEE, M-d H:m’)}</code>         </td>
         <td><code>Friday, 6-22 1:42</code>         </td>
      </tr>
      <tr>
         <td>DayOffset         </td>
         <td><code>${dayOffset('yymmdd', '-1')}</code>         </td>
         <td><span class="code">${dayOffset('yyMMdd', '-5')}</span> - returns 10<sup>th</sup> if today is 15<sup>th</sup> of August
formatted as per the specified format parameter - <span class="code">120810</span>.
<p><code>${</code><code>dayOffset('yyMMdd</code><code>', '+7')}</code> - returns 22<sup>th</sup> if today is 15<sup>th</sup> of August
formatted as per the specified format parameter - 120822.</p>
<p><code>${dayOffset('ddMMyy', '+1') ge '090414'}</code></p>         </td>
      </tr>
      <tr>
         <td>Random ID         </td>
         <td><code>${random()}</code>         </td>
         <td><code>C7F2119AAECEACCDE16C496C96FEEE39</code>         </td>
      </tr>
      <tr>
         <td>String Concatenation         </td>
         <td><code>${concat('str', 'ing')}</code>         </td>
         <td><code>string</code>         </td>
      </tr>
      <tr>
         <td>Substring         </td>
         <td><code>/${substring(stenv.loginname,0,1)}</code>
<p>where</p>
<p><code>stenv.loginname</code> is interoperable with <code>env['DXAGENT_LOGINNAME']</code></p>         </td>
         <td><code>string</code>         </td>
      </tr>
      <tr>
         <td>Force Exception         </td>
         <td><code>${error()}</code>         </td>
         <td><code>com.tumbleweed.util.expressions.InvalidExpressionException</code><br />
<code>Caused by: java.lang.Exception: Unspecified error</code>         </td>
      </tr>
      <tr>
         <td>Force Exception<br />
(with a specific error message)         </td>
         <td><code>${error(message)}</code>         </td>
         <td><code>com.tumbleweed.util.expressions.InvalidExpressionException Caused by: java.lang.Exception: An error has occurred in this part of the process!</code>         </td>
      </tr>
      <tr>
         <td>Full File Name         </td>
         <td><code>${filename($file)}</code>         </td>
         <td><code>filename.txt</code>         </td>
      </tr>
      <tr>
         <td>File Basename         </td>
         <td><code>${basename($file)}</code>         </td>
         <td><code>filename</code>         </td>
      </tr>
      <tr>
         <td>File Extension         </td>
         <td><code>${extension($file)}</code>         </td>
         <td><code>.txt</code>         </td>
      </tr>
      <tr>
         <td>Path Resolution         </td>
         <td><code>${resolve('.././path')}</code>         </td>
         <td>path         </td>
      </tr>
      <tr>
         <td>Path Resolution with Error         </td>
         <td><code>${resolve('../../..')}</code>         </td>
         <td><code>com.tumbleweed.util.expressions.</code><br />
<code>InvalidExpansionException: Invalid path resolution: /</code>         </td>
      </tr>
      <tr>
         <td>Path Resolution with Error         </td>
         <td><code>${resolve('\\')}</code>         </td>
         <td><code>com.tumbleweed.util.expressions.</code><br />
<code>InvalidExpansionException: Path must not contain '\' character</code>         </td>
      </tr>
   </tbody>
</table>
