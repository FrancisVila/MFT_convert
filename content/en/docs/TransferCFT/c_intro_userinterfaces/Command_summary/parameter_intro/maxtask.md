{
    "title": "maxtask",
    "linkTitle": "maxtask",
    "weight": "1930"
}<span id="maxtask"></span>

### maxtask

#### CFTPARM

**MAXTASK = { <u>8</u>
| n}    **

Enter the number of authorized file access tasks (default = 8). This refers to the number of authorized file access tasks, for example CFTTFIL. The used value may be recomputed, and be greater than the defined value, depending on the fixed number of files a task can handle on the system.

The following table indicates the maximum number supported for each
system.

> **Note:**
>
> When MAXTASK is set to one, a high TRANTASK value is useless.

<table>
   <thead>
      <tr>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">OS         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Maximum number supported         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>UNIX </p>         </td>
         <td><p>64</p>         </td>
      </tr>
      <tr>
         <td><p>Windows </p>         </td>
         <td><p>64</p>         </td>
      </tr>
      <tr>
         <td><p>z/OS (MVS)</p>         </td>
         <td><p>400</p>         </td>
      </tr>
      <tr>
         <td><p>IBM i</p>         </td>
         <td><p>64</p>         </td>
      </tr>
   </tbody>
</table>

The following CFTI18I  message displays in the CFTLOG when Transfer CFT is started so that you can view the actual MAXTRANS, MAXTASK, TRANTASK values.

Example



    CFTI18I+MAXTRANS=128, MAXTASK=16, TRANTASK=3

[Return to Command index](../../)
