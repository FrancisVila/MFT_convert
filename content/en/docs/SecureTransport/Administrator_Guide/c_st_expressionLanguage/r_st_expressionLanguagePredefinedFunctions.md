{
    "title": "Predefined functions",
    "linkTitle": "Predefined functions",
    "weight": "310"
}SecureTransport supports the following predefined functions:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
<th colspan="2">Name Syntax</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="2">Date<code>${date()}</code><br/>or<br/><code>${date(<em>date-and-time-pattern</em>)}</code>         </td>
         <td>Returns the current date and time. The <em>date-and-time pattern</em> is the same format defined in the Java class <code>java.text.SimpleDateFormat</code>. If no format is specified then the output is the default date format in the current locale.         </td>
      </tr>
      <tr>
         <td colspan="2">dayOffset <code>${dayOffset('yymmdd', 'var1')}</code>         </td>
         <td>Returns the current date and time with <span><code>var1</code></span> days  added or subtracted as an offset.         </td>
      </tr>
      <tr>
         <td colspan="2">Random ID<code>${random()}</code>         </td>
         <td>Creates a pseudo-random string using both letters and numbers. Format is a 32 byte hex string.         </td>
      </tr>
      <tr>
         <td colspan="2">String Concatenation<code>${concat(<em>var1</em>, <em>var2</em>)}</code>         </td>
         <td>Creates a new string concatenating the two variables together.         </td>
      </tr>
      <tr>
         <td colspan="2">Substring <code>${substring(variable, beginIndex,endIndex)}</code>         </td>
         <td>
            <p>Returns a substring for a given string.</p>
            <p>The substring begins at the specified <code>beginIndex</code> and 
 extends to the character at index <code>endIndex</code> - 1. Thus, the length of the substring is <code>endIndex-beginIndex</code>. </p>
         </td>
      </tr>
      <tr>
         <td colspan="2">Force Exception<code>${error()}</code> or <code>${error(<em>message</em>)}</code>         </td>
         <td>Throws an exception error. If <code>${error(<em>message</em>)}</code> is used, a message is returned with the error. This message is logged along with the exception.         </td>
      </tr>
      <tr>
         <td colspan="2">File Name<code>${filename(<em>variable</em>)}</code>         </td>
         <td>Returns the target file name with the extension, but without the path to the file.         </td>
      </tr>
      <tr>
         <td colspan="2">File Basename<code>${basename(<em>variable</em>)}</code>         </td>
         <td>Returns the target file name without the extension or path to the file.         </td>
      </tr>
      <tr>
         <td colspan="2">File Extension<code>${extension(<em>variable</em>)}</code>         </td>
         <td>Returns the target file extension, including the dot. If there is no extension, an empty string is returned.         </td>
      </tr>
      <tr>
         <td colspan="2"><code>${resolve()}</code>
         </td>
         <td>Removes any occurrence of ., or . in a file path. This function works with POSIX style paths only. If the resolved path is null, empty or returns a <code>/</code>, an error is returned.         </td>
      </tr>
   </tbody>
</table>

## Predefined function examples

The following table shows examples of the predefined functions:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Name</th>
         <th>Example usage</th>
         <th>Example return value</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Date (default)         </td>
         <td><code>${date()}</code>
         </td>
         <td><code>June 22, 2012 1:42:04 AM</code>
         </td>
      </tr>
      <tr>
         <td>Date (formatted)         </td>
         <td><code>${date('EEEE, M-d H:m’)}</code>
         </td>
         <td><code>Friday, 6-22 1:42</code>
         </td>
      </tr>
      <tr>
         <td>DayOffset         </td>
         <td><code>${dayOffset('yymmdd', '-1')}</code>
         </td>
         <td><span>${dayOffset('yyMMdd', '-5')}</span> - returns 10<sup>th</sup> if today is 15<sup>th</sup> of August 
 formatted as per the specified format parameter - <span>120810</span>.            <p><code>${</code><code>dayOffset('yyMMdd</code><code>', '+7')}</code> - returns 22<sup>th</sup> if today is 15<sup>th</sup> of August 
 formatted as per the specified format parameter - 120822.</p>            <p><code>${dayOffset('ddMMyy', '+1') ge '090414'}</code></p>         </td>
      </tr>
      <tr>
         <td>Random ID         </td>
         <td><code>${random()}</code>
         </td>
         <td><code>C7F2119AAECEACCDE16C496C96<br/>FEEE39</code>
         </td>
      </tr>
      <tr>
         <td>String Concatenation         </td>
         <td><code>${concat('str', 'ing')}</code>
         </td>
         <td><code>string</code>
         </td>
      </tr>
      <tr>
         <td>Substring          </td>
         <td><code>/${substring(stenv.loginname,0,1)}</code>
            <p>where </p>
            <p><code>stenv.loginname</code> is interoperable with <code>env['DXAGENT_LOGINNAME']</code></p>
         </td>
         <td><code>string</code>
         </td>
      </tr>
      <tr>
         <td>Force Exception         </td>
         <td><code>${error()}</code>
         </td>
         <td><code>com.tumbleweed.util.<br/>expressions.<br/>InvalidExpressionException</code>
<br/><code>Caused by: java.lang.Exception: Unspecified error</code>
         </td>
      </tr>
      <tr>
         <td>Force Exception <br/>(with a specific error message)         </td>
         <td><code>${error(<em>message</em>)}</code>
         </td>
         <td><code>com.tumbleweed.util.<br/>expressions.<br/>InvalidExpressionException Caused by: java.lang.Exception: An error has occurred in this part of the process!</code>
         </td>
      </tr>
      <tr>
         <td>Full File Name         </td>
         <td><code>${filename($file)}</code>
         </td>
         <td><code>filename.txt</code>
         </td>
      </tr>
      <tr>
         <td>File Basename         </td>
         <td><code>${basename($file)}</code>
         </td>
         <td><code>filename</code>
         </td>
      </tr>
      <tr>
         <td>File Extension         </td>
         <td><code>${extension($file)}</code>
         </td>
         <td><code>.txt</code>
         </td>
      </tr>
      <tr>
         <td>Path Resolution         </td>
         <td><code>${resolve('.././path')}</code>
         </td>
         <td>path         </td>
      </tr>
      <tr>
         <td>Path Resolution with Error         </td>
         <td><code>${resolve('../../..')}</code>
         </td>
         <td><code>com.tumbleweed.util.<br/>expressions.</code>
<br/><code>InvalidExpansionException: Invalid path resolution: /</code>
         </td>
      </tr>
      <tr>
         <td>Path Resolution with Error         </td>
         <td><code>${resolve('\\')}</code>
         </td>
         <td><code>com.tumbleweed.util.<br/>expressions.</code>
<br/><code>InvalidExpansionException: Path must not contain '\' character</code>
         </td>
      </tr>
   </tbody>
</table>
