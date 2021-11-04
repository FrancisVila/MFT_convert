{
    "title": "Gateway kernel prerequisites",
    "linkTitle": "Gateway kernel prerequisites",
    "weight": "40"
}## System V message IPC

Axway Gateway processes, created during monitor startup, run in the background.

All Gateway processes communicate with each other using the IPC message system services.

System parameters that address IPC message system resources must be checked and/or tuned depending on:

-   The maximum size of the messages exchanged between the monitor processes
-   The maximum number of processes Gateway may have started at any time

**Sun Solaris 10** uses resource controls instead of tunable parameters - refer to the table at the end of this section for further information.

Interactive tools, such as `peladm, peldsp`, and so on, share a unique message queue multiplexed by pid. For purposes of performance, each background process started by Gateway uses a separate message queue for incoming messages. The maximum number of message queues that Gateway can use at any time (addressed by the MSGMNI system parameter) must be calculated in the following way:

> **1 + number of Gateway processes**

For a complete Axway Gateway installation, this number will not exceed 50, provided that you use default values for configuration parameters.

The following IPC parameter values are suitable for Gateway to run when configured with default values and full file transfer features, provided that the corresponding system resources are available for Gateway use.

### IPC parameter values

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter name         </th>
<th class="HeadD-Column1-Header1">Minimum value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>MSGMAP</p>         </td>
         <td>100         </td>
      </tr>
      <tr>
         <td>MSGMAX         </td>
         <td>32768         </td>
      </tr>
      <tr>
         <td>MSGMNB         </td>
         <td>65535         </td>
      </tr>
      <tr>
         <td>MSGMNI         </td>
         <td>100         </td>
      </tr>
      <tr>
         <td>MSGSSZ         </td>
         <td>8         </td>
      </tr>
      <tr>
         <td>MSGTQL         </td>
         <td>100         </td>
      </tr>
      <tr>
         <td>MSGSEG         </td>
         <td>16384         </td>
      </tr>
   </tbody>
</table>

When the product is configured for either SNA LU 6.2 or for dynamic file transfer processes, the total number of running Gateway processes may exceed 50. You may then need to adjust the parameter values related to IPC resources accordingly.

The maximum number of message queues that Gateway needs can be deduced from the file `run_time/etc/conffile` since it is the number of times the line of the format `queue <number>` occurs in this file. Consequently, the output of the following simple shell command can be used to obtain the value for the `MSGMNI `system parameters.

`cat run_time/etc/conffile | grep ‘queue ‘ | wc`

If Gateway is not the only application that can use IPC message services on your system, you must size the corresponding parameters depending on the requirements of all applications running simultaneously.

The memory pool size corresponding to the parameter values provided above is MSGSSZ\*MSGSEG = 128 KB. The following sample configures a memory pool size of MSGSSZ\*MSGSEG = 512 KB.

If your UNIX system can support a higher size for this pool, it is recommended to increase this pool size to up to four times the suggested values. For example: MSGSSZ = 16 and MSGSEG = 131072 defines a memory pool of 2 MebiOctets.

### Larger IPC parameter values for 200 message queues (200 processes max)

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter name         </th>
<th class="HeadD-Column1-Header1">Minimum value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>MSGMAP         </td>
         <td>200         </td>
      </tr>
      <tr>
         <td>MSGMAX         </td>
         <td>32768         </td>
      </tr>
      <tr>
         <td>MSGMNB         </td>
         <td>65535         </td>
      </tr>
      <tr>
         <td>MSGMNI         </td>
         <td>200         </td>
      </tr>
      <tr>
         <td>MSGSSZ         </td>
         <td>16         </td>
      </tr>
      <tr>
         <td>MSGTQL         </td>
         <td>200         </td>
      </tr>
      <tr>
         <td>MSGSEG         </td>
         <td>32768         </td>
      </tr>
   </tbody>
</table>

Gateway can handle any MSGMAX value, either by compressing or segmenting the message data if needed. However, a system parameter value that is too small can affect performance significantly. Using a suitable value (as recommended in the tables above) ensures that all Gateway IPC messages will neither be fragmented nor compressed.

Gateway programs need to know the value of MSGMAX in order to handle IPC messages larger than this value correctly. Since there is no system service under UNIX that enables you to get this information, the environment variable p\_smw\_msg\_max is used to pass the MSGMAX value to Gateway programs. This value is estimated during Gateway installation and the corresponding shell commands are inserted into the Gateway profile (`run_time/etc/profile` file).

As a result, when the value of MSGMAX is changed, and in order for Gateway to take the new value into account, the Gateway profile must be changed accordingly. Configuring and then restarting the product can achieve this. It is also possible to edit `run_time/etc/profile` and apply the change manually.

The line in the Gateway profile that applies to the MSGMAX system parameter value is of the following format:

`p_smw_msg_max=16384; export p_smw_msg_max`

### IPC resource controls on Sun Solaris 10

Your system administrator should check, and if necessary modify, the following resource control values using the prctl command. The values used depend on the load on your Gateway.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Resource control         </th>
<th class="HeadD-Column1-Header1">Recommended value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>max-msg-qbytes         </td>
         <td>1 or 2 MB         </td>
      </tr>
      <tr>
         <td>max-msg-messages         </td>
         <td>66.6 K         </td>
      </tr>
   </tbody>
</table>

Depending on your system configuration, the system administrator may need to modify the resource controls at zone, project, or process levels.

In addition, your system administrator should set `ulimit open files` to 4096.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
