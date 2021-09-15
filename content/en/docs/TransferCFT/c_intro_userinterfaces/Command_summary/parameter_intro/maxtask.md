{
    "title": "maxtask",
    "linkTitle": "maxtask",
    "weight": "1960"
}### <span id="maxtask"></span>maxtask

#### CFTPARM

**MAXTASK = { <u>8</u>
| n}    **

Enter the number of authorized file access tasks (default = 8). This refers to the number of authorized file access tasks, for example CFTTFIL. The used value may be recomputed, and be greater than the defined value, depending on the fixed number of files a task can handle on the system.

The following table indicates the maximum number supported for each
system.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When MAXTASK is set to one, a high TRANTASK value is useless.         </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>OS</th>
         <th>Maximum number supported</th>
      </tr>
   </thead>
      <tr>
         <td valign="top">
            <p>UNIX </p>
         </td>
         <td valign="top">
            <p>64</p>
         </td>
      </tr>
      <tr>
         <td valign="top">
            <p>Windows </p>
         </td>
         <td valign="top">
            <p>64</p>
         </td>
      </tr>
      <tr>
         <td valign="top">
            <p>z/OS (MVS)</p>
         </td>
         <td valign="top">
            <p>400</p>
         </td>
      </tr>
      <tr>
         <td valign="top">
            <p>IBM i</p>
         </td>
         <td valign="top">
            <p>64</p>
         </td>
      </tr>
</table>

The following CFTI18I  message displays in the CFTLOG when Transfer CFT is started so that you can view the actual MAXTRANS, MAXTASK, TRANTASK values.

Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTI18I+MAXTRANS=128, MAXTASK=16, TRANTASK=3</p>
         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
