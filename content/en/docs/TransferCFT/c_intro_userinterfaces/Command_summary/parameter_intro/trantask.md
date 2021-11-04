{
    "title": "trantask",
    "linkTitle": "trantask",
    "weight": "3570"
}<span id="trantask"></span>

### trantask

#### CFTPARM

\[TRANTASK = <u>3</u> | n \]

The maximum number of parallel transfers that a task can handle before starting another task (file access task). The value used may differ from the set value when the TRANTASK is greater than the MAXTRANS/MAXTASK value.

If the number of file access tasks authorized is reached (MAXTASK), additional transfers in parallel (up to MAXTRANS) are divided equally between the least loaded file access tasks.

The MAXTASK value multiplied by the TRANTASK value should be less than or equal to MAXTRANS.

The following table indicates the maximum value supported for each system, where 3 is the default for all systems.

<table>
         
         
         
   
   <th>
      <tr>
<th><p>Operating system </p>         </th>
<th><p>Maximum value </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Windows</p>         </td>
         <td><p>1000</p>         </td>
      </tr>
      <tr>
         <td><p>UNIX/HP Nonstop</p>         </td>
         <td><p>64</p>         </td>
      </tr>
      <tr>
         <td><p>z/OS (MVS)</p>         </td>
         <td><p>64</p>         </td>
      </tr>
      <tr>
         <td><p>IBM i (OS400)</p>         </td>
         <td><p>64</p>         </td>
      </tr>
   </tbody>
</table>

**Example**

MAXTRANS = 14,  
MAXTASK = 2,  
TRANTASK = 4,

This configuration creates 2 file access tasks, each handling 4 transfers. Transfers one through eight are assigned to the two tasks (as there are four transfers for each task). Transfers nine to fourteen are divided equally between the two tasks until seven transfers per task, MAXTRANS÷MAXTASK, is reached. From the fifteenth transfer on (15 is greater than MAXTRANS), all new transfers are put on hold until resources become available.

[Return to Command index](../../)